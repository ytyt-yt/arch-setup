# archlinux setup

## Installation

[https://wiki.archlinux.org/index.php/installation_guide](https://wiki.archlinux.org/index.php/installation_guide)

* Boot loader: [systemd-boot](https://wiki.archlinux.org/index.php/Systemd-boot)
  * if share EFI partition: mount to `/boot/efi/` and add [systemd hook](https://wiki.archlinux.org/index.php/EFI_system_partition#Using_systemd) 
* intel-ucode
* [UTC in Windows](https://wiki.archlinux.org/index.php/Time#Time_standard)
* Enable [dhcpcd](https://wiki.archlinux.org/index.php/Dhcpcd)

## Post-installation

### Add User
[Group List](https://wiki.archlinux.org/index.php/Users_and_groups#Group_list)

```bash
useradd -m -G adm,log,rfkill,sys,users,uucp,wheel -s /bin/bash yt
EDITOR=nano visudo
```
```
%wheel      ALL=(ALL) ALL
```

### config bash
```
$ sudo pacman -S bash-completion pkgfile autojump
$ sudo pkgfile -u
```
sync `.bashrc`

### AUR
[Trizen](https://github.com/trizen/trizen)
