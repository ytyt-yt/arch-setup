# archlinux setup

## Installation

[https://wiki.archlinux.org/index.php/installation_guide](https://wiki.archlinux.org/index.php/installation_guide)


* intel-ucode
* Boot loader: [systemd-boot](https://wiki.archlinux.org/index.php/Systemd-boot)
  * if share EFI partition:
    * Option 1: mount to `/boot/efi/` and add [systemd hook](https://wiki.archlinux.org/index.php/EFI_system_partition#Using_systemd) 
    * Option 2: [XBOOTLDR](https://wiki.archlinux.org/title/Systemd-boot#Installation_using_XBOOTLDR) (EFI partition might be small)
      * `/boot`
        * type: "Linux extended boot" (`bc13c2ff-59e6-4262-a352-b275fd6f7172`)
        *  **FAT32** (`mkfs.vfat -F 32 xxx`, ext4 won't work)
      * mount EFI to `/efi`
      * add arch.conf to `/boot/loader/entries/*.conf`
      * update `/efi/loader/loader.conf`
* [UTC in Windows](https://wiki.archlinux.org/index.php/Time#Time_standard)
* Network: Install [NetworkManager](https://wiki.archlinux.org/title/NetworkManager) or Enable [dhcpcd](https://wiki.archlinux.org/index.php/Dhcpcd)

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
