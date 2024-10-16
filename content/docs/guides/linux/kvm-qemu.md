---
title: "Kvm Qemu"
description: ""
summary: ""
date: 2024-10-15T20:51:42+02:00
lastmod: 2024-10-15T20:51:42+02:00
draft: false
weight: 999
toc: true
seo:
  title: "kvm-qemu" # custom title (optional)
  description: "" # custom description (recommended)
  canonical: "" # custom canonical URL (optional)
  noindex: false # false (default) or true
---

## GPU-Passthrough

For GPU-Passthrough in qemu it's **important** to know, that you first need a NVIDIA GPU and for the drivers to work, you have to do some things in the xml file of the VM you're trying to pass the GPU through.

The first two big things here are the [kvm hidden flag](#the-hidden-kvm-flag) and the [hyperv vendor_id](#vendor_id). After this, you can install the NVIDIA drivers inside your VM. If you don't follow these steps, your VM will not have the full power with the GPU, and you might not even be able to install the drivers, due to virtual limitations.

### the hidden kvm flag

```xml
<features>
  ...
<kvm>
  <hidden state="on"/>
</kvm>
  ...
</features>

```

### vendor_id

```xml
<features>
  ...
<hyperv>
   <vendor_id state="on" value="whatever"/>
</hyperv>
  ...
</features>

```

## virtualization support

To get things like WSL to work under qemu in linux, you can add the following feature to your xml:

<!-- ### virtualization support -->

```xml
<feature policy='require' name='vmx' />
```

## looking-glass

Use this with you looking glass config to enable more resolutions and higher refresh rates! Be sure to disable the memballoon thing. This was the problem the last times for me, when i couldnt get my 3440x1440 monitor to work.

```xml
<devices>
..
<memballoon model="none"/>
    <shmem name="looking-glass">
      <model type="ivshmem-plain"/>
      <size unit="M">128</size>
      <address type="pci" domain="0x0000" bus="0x10" slot="0x01" function="0x0"/>
    </shmem>
</devices>


```
