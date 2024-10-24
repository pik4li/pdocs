---
title: "KVM QEMU GPU Passthrough Guide"
description: "A guide to setting up GPU passthrough with KVM and QEMU, enabling virtualization support, and configuring Looking Glass."
summary: "Learn how to set up GPU passthrough with NVIDIA GPUs in KVM/QEMU, configure vendor flags, enable virtualization for WSL, and optimize Looking Glass for high resolutions and refresh rates."
date: 2024-10-15T20:51:42+02:00
lastmod: 2024-10-15T20:51:42+02:00
draft: false
weight: 999
toc: true
seo:
  title: "KVM QEMU GPU Passthrough Setup"
  description: "A comprehensive guide to GPU passthrough with KVM/QEMU, configuring NVIDIA GPUs, and optimizing Looking Glass."
  canonical: ""
  noindex: false
---

# **KVM QEMU: GPU Passthrough and Virtualization Support**

This guide covers essential steps for setting up GPU passthrough in a KVM/QEMU virtual machine with an NVIDIA GPU. It also details enabling virtualization support and configuring Looking Glass for enhanced performance.

---

## **1. GPU Passthrough Setup**

When setting up GPU passthrough in QEMU, **two key elements** need attention for NVIDIA GPUs: the [hidden KVM flag](#the-hidden-kvm-flag) and the [vendor ID for Hyper-V](#vendor_id).

Without properly configuring these elements, the VM will not recognize or fully utilize the GPU's power, and installing NVIDIA drivers may fail due to virtualization restrictions.

### **1.1. Hidden KVM Flag**

Enabling the hidden KVM flag prevents NVIDIA drivers from detecting the virtual machine, allowing the GPU passthrough to work correctly.

```xml
<features>
  ...
  <kvm>
    <hidden state="on"/>
  </kvm>
  ...
</features>
```

### **1.2. Vendor ID for Hyper-V**

Set a custom `vendor_id` in the XML file of your VM. This helps in fooling the drivers into thinking the VM is running on actual hardware.

```xml
<features>
  ...
  <hyperv>
    <vendor_id state="on" value="whatever"/>
  </hyperv>
  ...
</features>
```

---

## **2. Enabling Virtualization Support**

To run certain features like **Windows Subsystem for Linux (WSL)** within your virtual machine, ensure that **Intel VT-x** or **AMD-V** virtualization support is enabled. This can be done by adding the following line to your XML configuration:

```xml
<feature policy='require' name='vmx'/>
```

---

## **3. Optimizing Looking Glass for High Resolutions**

**Looking Glass** is a tool that allows you to share the GPU between the host and guest, providing a smooth KVM experience without needing a second monitor.

### **3.1. Disabling Memory Ballooning**

In some cases, **memory ballooning** may prevent Looking Glass from working with higher resolutions (such as 3440x1440). You can disable this feature in your VM’s XML configuration:

```xml
<devices>
  ...
  <memballoon model="none"/>
  <shmem name="looking-glass">
    <model type="ivshmem-plain"/>
    <size unit="M">128</size>
    <address type="pci" domain="0x0000" bus="0x10" slot="0x01" function="0x0"/>
  </shmem>
</devices>
```

By disabling `memballoon`, you should be able to get higher refresh rates and more resolutions to work seamlessly.

---

### **Tips & Troubleshooting**

- **NVIDIA Code 43**: If you encounter this error when using an NVIDIA GPU, ensure the hidden KVM flag is properly configured.
- **Looking Glass Performance**: Adjust the shared memory size in the `shmem` section to fine-tune performance. Increasing this may improve the VM's ability to handle high frame rates and resolutions.

---

This guide should help you configure your virtual machines with KVM/QEMU to achieve GPU passthrough with optimal performance. Let me know if you need further adjustments or additional sections.
