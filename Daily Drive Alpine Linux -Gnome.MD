### Daily Driving Alpine Linux

**Ready-to-use installation and post-install guide for a daily-driver Alpine Linux desktop.**  
**Note:** Replace every occurrence of `<your-username>` with the username you created during setup.

---

### Installation

#### Partitioning and boot
Create two partitions for example:
- **FAT32 1GB** for `boot,esp`
- **EXT4 60GB** for `root`  
(Example: use GParted USB)

#### Boot installer
Boot the Alpine Linux image and log in as `root` (no password).

**Dual boot install**
```sh
# mount root and boot partitions (replace devices)
mount -t ext4 /dev/yourpartition1 /mnt
mount -t vfat /dev/yourpartition2 /mnt/boot

# run installer
setup-alpine

# install to mounted disk
setup-disk -m sys /mnt

# reboot when finished
reboot
```
When running `setup-alpine` for dual boot, answer **none** at the prompt that asks about storing data.

**Non-dual boot (wipe entire disk)**
```sh
setup-alpine
```

---

### Post Install Setup

#### Basic packages and repos
Log in as `root` and run:
```sh
apk add nano
# edit repositories to enable community repo
nano /etc/apk/repositories
apk update && apk upgrade
apk add bash bash-completion sudo shadow
```

#### Add user and sudo
```sh
# allow wheel group to use sudo
echo '%wheel ALL=(ALL) ALL' > /etc/sudoers.d/wheel

# add your user to wheel and set shell to bash
adduser <your-username> wheel
usermod -s /bin/bash <your-username>

# reboot to apply
reboot
```

---

### Desktop GNOME

#### Install GNOME and fonts
Log in as your user and run:
```sh
sudo setup-xorg-base
sudo setup-desktop gnome
sudo apk add gnome-apps-core
sudo rc-update add apk-polkit-server default

# fonts and MS fonts installer
sudo apk add font-terminus font-inconsolata font-dejavu font-noto font-noto-cjk font-awesome font-noto-extra font-liberation msttcorefonts-installer
sudo update-ms-fonts && sudo fc-cache -f
```

#### Disable acpid (conflicts with elogind)
```sh
sudo rc-update del acpid
```

---

### Networking Bluetooth Sound Printers Flatpak Packages Power

#### Network Manager
```sh
sudo apk add networkmanager-wifi wpa_supplicant
sudo rc-service networkmanager start
sudo rc-update add networkmanager default

# add user to plugdev
sudo addgroup plugdev
sudo adduser <your-username> plugdev
```

Edit `/etc/NetworkManager/NetworkManager.conf`:
```ini
[main]
plugins=keyfile

[device]
wifi.scan-rand-mac-address=yes
wifi.backend=wpa_supplicant
```

Disable the legacy `networking` service:
```sh
sudo rc-service networking stop
sudo rc-update del networking boot
```

Allow any user to change network config:
```sh
sudo mkdir -p /etc/NetworkManager/conf.d
sudo tee /etc/NetworkManager/conf.d/any-user.conf > /dev/null <<'EOF'
[main]
auth-polkit=false
EOF

sudo reboot
```

#### Bluetooth
```sh
sudo setup-devd udev
sudo apk add bluez
sudo adduser <your-username> lp
sudo adduser root lp
sudo rc-update add bluetooth default
sudo reboot
```

#### Sound (SOF, PipeWire, WirePlumber)
```sh
# if sof-firmware needed
sudo apk add sof-firmware
sudo reboot

# pipewire stack
sudo apk add pipewire wireplumber pipewire-pulse bluez-openrc pipewire-spa-bluez

# add users to audio/video groups
sudo adduser <your-username> audio
sudo adduser root audio
sudo adduser <your-username> video
sudo adduser root video

sudo reboot
```

#### Printers using CUPS
```sh
sudo apk add cups cups-libs cups-client cups-filters libusb ghostscript python3 py-reportlab libjpeg libjpeg-turbo net-snmp
sudo rc-update add cupsd boot
sudo reboot
```

#### Flatpak
```sh
sudo apk add flatpak
flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo
```

#### Recommended packages (example for Intel graphics)
```sh
sudo apk add curl wget git xz unzip zip vim gptfdisk e2fsprogs mtools mlocate ntfs-3g fuse-exfat linux-headers gtksourceview4 ffmpeg htop mesa-dri-gallium mesa-va-gallium intel-media-driver
```

#### Development packages
```sh
sudo apk add autoconf automake bison m4 make libtool flex meson ninja optipng sassc
```

#### Power savings
```sh
sudo apk add tlp tlp-rdw powertop
sudo rc-update add tlp boot
sudo reboot
```

#### Search and install apps
- Search packages: `apk search <term>`
- Install with apk: `sudo apk add <package>`
- Install Flatpak apps: `flatpak install flathub <app-id>`

---

### Optional Extras

#### Aliases
Add aliases to your shell config.

**Bash**
```sh
nano ~/.bashrc
```

**Zsh**
```sh
nano ~/.zshrc
```

Add these lines to the bottom (customize as desired):
```sh
alias service='sudo rc-service'
alias install='sudo apk add'
alias remove='sudo apk del'
alias search='apk search'
alias reboot='sudo reboot'
alias poweroff='sudo poweroff'
alias update='sudo apk update && sudo apk upgrade && flatpak update -y'
```

#### Mount drives on boot
Edit `/etc/fstab` and add a line for each drive to mount at boot. Example:
```fstab
/dev/yourdriveorpartition /mnt/Foldertomountinto ext4 nosuid,nodev,nofail 0 0
```
Example entry:
```fstab
/dev/nvme0n1p6 /mnt/Storage ext4 nosuid,nodev,nofail 0 0
```

---

### Quick Tips
- Replace `<your-username>` everywhere with your actual username.
- Use `sudo rc-update show` and `sudo rc-status` to inspect services.
- Keep system updated: `sudo apk update && sudo apk upgrade` and `flatpak update -y`.

---
