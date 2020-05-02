# archconfig
Scripts for installing and configuring Arch Linux using my dotfiles

## Usage
### Installing Arch Linux from scratch (based on Arch Wiki)
Assumptions:
- Booted into Arch Linux install media
- Working internet connection
  
Run
```
wget shahzebs.github.io/archconfig
```
to download install script (copy of `installarchlinux`). Execute the script by running `bash archconfig`.
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
