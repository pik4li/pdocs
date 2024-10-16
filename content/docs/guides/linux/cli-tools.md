---
title: "Cli Tools"
description: ""
summary: ""
date: 2024-10-16T09:16:31+02:00
lastmod: 2024-10-16T09:16:31+02:00
draft: false
weight: 999
toc: true
seo:
  title: "" # custom title (optional)
  description: "" # custom description (recommended)
  canonical: "" # custom canonical URL (optional)
  noindex: false # false (default) or true
---

#### ncdu - NCurses Disk Usage

With ncdu an overview of the used space for all folders can be displayed very quickly:

```bash
sudo apt install ncdu

```

After Installation for example the Root-Partition can be scanned using the following command:

```bash
sudo ncdu / -x

```

The Parameter -x excludes other mounted Disks (Do not cross filesystem boundaries, i.e. only count files and directories on the same filesystem as the directory being scanned.)

---

## **bat || better than cat**

<details><summary>Preview</summary>

```ruby
───────┬─────────────────────────────────────────────────────────────────────────────────────────────
       │ File: docker-compose.yml
───────┼─────────────────────────────────────────────────────────────────────────────────────────────
   1   │ version: "3.8"
   2   │ services:
   3   │   dashy:
   4   │     image: lissy93/dashy
   5   │     container_name: Dashy
   6   │     # Pass in your config file below, by specifying the path on your host machine
   7   │     volumes:
   8   │       - ./data/conf.yml:/app/public/conf.yml
   9   │     ports:
  10   │       - 9000:80
  11   │     # Set any environmental variables
  12   │     environment:
  13   │       - NODE_ENV=production
  14   │     # Specify your user ID and group ID. You can find this by running `id -u` and `id -g`
  15   │       - UID=1000
  16   │       - GID=1000
  17   │     # Specify restart policy
  18   │     restart: unless-stopped
  19   │     # Configure healthchecks
  20   │     healthcheck:
  21   │       test: ['CMD', 'node', '/app/services/healthcheck']
  22   │       interval: 1m30s
  23   │       timeout: 10s
  24   │       retries: 3
  25   │       start_period: 40s
───────┴─────────────────────────────────────────────────────────────────────────────────────────────

```

</details>

##### Overview

"bat" is just the better cat. It's colorful and a bit more stylish. Be sure to use it either with an Alias which automatically sets you the <span style="color: rgb(230, 126, 35);">"**--paging=never**"</span> flag or remember to use the flag by yourself.

---

## **Pfetch**

<details><summary>Preview</summary>

```julia
root@srv-docker ~# pfetch
         _    root@srv-docker
     ---(_)   os     Ubuntu 23.04
 _/  ---  \   host   OptiPlex 3050
(_) |   |     kernel 5.15.102-1-pve
  \  --- _/   uptime 4d 13h 57m
     ---(_)   pkgs   439
              memory 1051M / 6144M

```

```kotlin
╭─piecka@srvdocker /root  ‹system›
╰─$ pfetch
  _____      piecka@srvdocker
 /  __ \     os     Debian GNU/Linux 12 (bookworm)
|  /    |    host   OptiPlex 3050
|  \___-     kernel 6.2.16-4-pve
-_           uptime 17h 7m
  --_        pkgs   481
             memory 1159M / 12288M


```

</details>

#### Installation

Dependencies:

- git

```bash
git clone https://github.com/dylanaraps/pfetch.git && sudo cp pfetch/pfetch /bin/ && sudo rm -r pfetch/ && pfetch

```

---
