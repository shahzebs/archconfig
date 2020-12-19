# archconfig
Scripts for installing and configuring Arch Linux using my dotfiles

## Usage
### Installing Arch Linux from scratch (based on Arch Wiki)
Assumptions:
- Booted into Arch Linux install media
- Working internet connection
  
Run
```
curl -L shahzebs.github.io/archconfig > installarchlinux
```
to download install script (copy of `installarchlinux`). Execute the script by running `bash installarchlinux`.
The user will be taken through some interactable checkpoints and installation steps like partitioning disk, selecting favorite mirrors, entering hostname, creating a user and choosing passwords for both root and created user, etc.
The Arch Linux install is a barebones install without any graphical environment like described in the [Installation Guide](https://wiki.archlinux.org/index.php/Installation_guide) of Arch Wiki.
After the script exits succesfully, the user can boot into the fresh install and decide to clone this repository to continue configuring the system.

### Configuring a fresh install
The configuration is based on my dotfiles at [shahzebs/dotfiles](https://github.com/shahzebs/dotfiles).

Assumptions:
- Completely fresh install
- Working internet connection

Clone this repository (`git clone https://github.com/shahzebs/archconfig.git`) and run
```
archconfig/configurearchlinux
```
to begin configuration.
The script will clone my dotfiles repo and apply changes to the home directory followed by installing packages like Xorg utilities, fonts, notification utilities, alsa and pulseaudio, zathura, etc. Furthermore, it will install yay (AUR helper) and set up my vim and git config. The script ends with installing the window manager (dwm), terminal emulator (st) and dmenu.

### Virtualbox
If configuring for an Arch Linux guest in Virtualbox remember to install Virtualbox Guest Additions. See the [Arch Wiki](https://wiki.archlinux.org/index.php/VirtualBox/Install_Arch_Linux_as_a_guest#Install_the_Guest_Additions) for more details. Here's a summary:

- Begin by inserting the Guest Additions CD image from `Device > Insert Guest Additions CD image` in Virtualbox (versions of guest additions must be same in host and guest). 
- Install the package `virtualbox-guest-iso` from within the Arch Linux guest.
- Mount the image from within the Arch Linux guest to e.g. `/mnt/` and execute `VBoxLinuxAdditions.run` as root.
- If for any reason the guest additions don't compile (e.g. due to missing `linux-headers`), the vbox kernel modules can be recompiled with `rcvboxadd setup` as root.
- Finally, run `VBoxClient-all` to activate services for shared clipboard, seamless mode, auto-resizing, etc. (shared clipboard must be enabled in Virtualbox settings too).
