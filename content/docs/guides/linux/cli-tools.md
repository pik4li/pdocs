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

## **Disk Usage & System Overview Tools**

### **1. ncdu - NCurses Disk Usage**

`ncdu` is a fast and easy-to-use tool that provides an overview of disk usage. It helps in visualizing and managing disk space.

#### Installation:

{{< tabs >}}
{{< tab "Debian/Ubuntu" >}}

```bash
sudo apt install ncdu
```

{{< /tab >}}
{{< tab "Fedora" >}}

```bash
sudo dnf install ncdu
```

{{< /tab >}}
{{< tab "OpenSuse" >}}

```bash
sudo zypper install ncdu
```

{{< /tab >}}
{{< tab "Arch" >}}

```bash
sudo pacman -S ncdu
```

{{< /tab >}}
{{< /tabs >}}

#### Usage:

```bash
sudo ncdu / -x
```

- `-x` ensures that only the current filesystem is scanned.

---

## **2. bat - A Better `cat`**

`bat` is a better alternative to `cat`, with syntax highlighting, line numbers, and paging capabilities.

#### Installation:

{{< tabs >}}
{{< tab "Debian/Ubuntu" >}}

```bash
sudo apt install bat
```

{{< /tab >}}
{{< tab "Fedora" >}}

```bash
sudo dnf install bat
```

{{< /tab >}}
{{< tab "OpenSuse" >}}

```bash
sudo zypper install bat
```

{{< /tab >}}
{{< tab "Arch" >}}

```bash
sudo pacman -S bat
```

{{< /tab >}}
{{< /tabs >}}

#### Usage:

```bash
bat <file>
```

For convenience, use the following alias:

```bash
alias bat="bat --paging=never"
```

---

## **3. Pfetch - Minimal System Information**

`Pfetch` is a minimal and customizable system information tool.

#### Installation:

```bash
git clone https://github.com/dylanaraps/pfetch.git
sudo cp pfetch/pfetch /bin/
sudo rm -r pfetch/
```

#### Usage:

```bash
pfetch
```

---

## **4. exa - Modern Replacement for `ls`**

`exa` is a modern alternative to `ls`, with features like tree views and file type icons.

#### Installation:

{{< tabs >}}
{{< tab "Debian/Ubuntu" >}}

```bash
sudo apt install exa
```

{{< /tab >}}
{{< tab "Fedora" >}}

```bash
sudo dnf install exa
```

{{< /tab >}}
{{< tab "OpenSuse" >}}

```bash
sudo zypper install exa
```

{{< /tab >}}
{{< tab "Arch" >}}

```bash
sudo pacman -S exa
```

{{< /tab >}}
{{< /tabs >}}

#### Usage:

```bash
exa -la
```

---

## **5. fzf - Fuzzy Finder**

`fzf` is an interactive fuzzy search tool.

#### Installation:

{{< tabs >}}
{{< tab "Debian/Ubuntu" >}}

```bash
sudo apt install fzf
```

{{< /tab >}}
{{< tab "Fedora" >}}

```bash
sudo dnf install fzf
```

{{< /tab >}}
{{< tab "OpenSuse" >}}

```bash
sudo zypper install fzf
```

{{< /tab >}}
{{< tab "Arch" >}}

```bash
sudo pacman -S fzf
```

{{< /tab >}}
{{< /tabs >}}

#### Usage:

```bash
fzf
```

---

## **6. htop - Interactive Process Viewer**

`htop` is an interactive process viewer with a user-friendly interface.

#### Installation:

{{< tabs >}}
{{< tab "Debian/Ubuntu" >}}

```bash
sudo apt install htop
```

{{< /tab >}}
{{< tab "Fedora" >}}

```bash
sudo dnf install htop
```

{{< /tab >}}
{{< tab "OpenSuse" >}}

```bash
sudo zypper install htop
```

{{< /tab >}}
{{< tab "Arch" >}}

```bash
sudo pacman -S htop
```

{{< /tab >}}
{{< /tabs >}}

#### Usage:

```bash
htop
```

---

## **7. tldr - Simplified Command Documentation**

`tldr` provides simplified and concise examples of common commands.

#### Installation:

{{< tabs >}}
{{< tab "Debian/Ubuntu" >}}

```bash
sudo apt install tldr
```

{{< /tab >}}
{{< tab "Fedora" >}}

```bash
sudo dnf install tldr
```

{{< /tab >}}
{{< tab "OpenSuse" >}}

```bash
sudo zypper install tldr
```

{{< /tab >}}
{{< tab "Arch" >}}

```bash
sudo pacman -S tldr
```

{{< /tab >}}
{{< /tabs >}}

#### Usage:

```bash
tldr <command>
```

---

This structure with tabs allows users of different distributions to easily find the installation commands for the package managers they use. Let me know if you'd like any further refinements!
