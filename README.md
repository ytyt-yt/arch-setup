# archlinux setup

## Installation

[https://wiki.archlinux.org/index.php/installation_guide#Post-installation](https://wiki.archlinux.org/index.php/installation_guide#Post-installation)

* Boot loader: [systemd-boot](https://wiki.archlinux.org/index.php/Systemd-boot)
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
$ sudo pacman -S bash-completion autojump
```
sync `.bashrc`

### pacaur
[pacaur_install.sh](https://gist.github.com/Tadly/0e65d30f279a34c33e9b)
