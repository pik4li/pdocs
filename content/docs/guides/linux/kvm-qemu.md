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

The hidden_kvm state enables you to install the NVIDIA drivers in the vm. Edit the xml file of the desired Windows-VM.

```xml
<features>
  ...
<kvm>
  <hidden state="on"/>
</kvm>
  ...
</features>


```

The vendor id also has to be present, to ensure the NVIDIA driver can be installed.

```xml
<features>
  ...
<hyperv>
   <vendor_id state="on" value="whatever"/>
</hyperv>
  ...
</features>


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
