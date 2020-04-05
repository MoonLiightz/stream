# Stream #008 (2020-03-17)

**Main topic:** Arch Linux on old hardware

## Topics

### Arch Linux on old hardware

I have multiple old systems at home and therefore it's easy to build a system for testing. I thought it would be a nice idea to install Arch Linux on a system.
Several years ago I used Arch more or less productive in a dual boot setup with Windows.

This was the hardware I used in this stream:

- [MSI E350IA-E45](https://de.msi.com/Motherboard/E350IAE45.html)
- A old case
- A 400 watt PSU
- A old notebook harddrive (500GB / 7200 rpm)

Before the stream I created a Arch boot usb stick (4GB). I downloaded the archiso and made the stick using [Rufus](https://rufus.ie/).

#### Installation

In the stream I followed [this tutorial](https://wiki.archlinux.org/index.php/installation_guide) so I will not write down every step I did. It would be the same as the tutorial though.
After installing the base system I chose [GRUB](https://de.wikipedia.org/wiki/Grand_Unified_Bootloader) as [bootloader](https://wiki.archlinux.org/index.php/Arch_boot_process#Boot_loader), using [this doc](https://wiki.archlinux.org/index.php/GRUB#Installation) for installation.

#### Configuring the system

[Xorg](https://de.wikipedia.org/wiki/X.Org-Server) seems like to still be the go to standard. After installing [Xorg](https://de.wikipedia.org/wiki/X.Org-Server) I tried [Xfce](https://de.wikipedia.org/wiki/Xfce) but I still don't like it and we ended up using [Plasma](https://kde.org/plasma-desktop). It was quite easy to install it.

```bash
pacman -Syu plasma-meta konsole dolphin
```

Adding a `.xinitrc` file in the home of my own user which I created earlier with `useradd -m -s /bin/bash fabian`.

The content of the `.xinitrc` has to be

```sh
exec startplasma-x11
```

Because I don't like this windowsish UI, CodeCereal suggested me to remove the whole panel at the bottom and use `latte-dock`. So we ended up installing it with

```bash
pacman -Syu latte-dock
```
