# archconfig
Scripts for installing and configuring Arch Linux using my dotfiles

## Usage
### Installing Arch Linux from scratch
Assumptions:
- Booted into Arch Linux install media
- Working internet connection
  
Enter 
```
wget shahzebs.github.io/archconfig
```
to download install script. Execute the script by entering `bash archconfig`.
The user will be taken through some interactable checkpoints and installation steps like partitioning disk, selecting favorite mirrors, entering hostname, creating a user and choosing passwords for both root and ceated user, etc.
After install, the user can boot into the fresh install and decide to clone this repository to continue configuring the system.

### Configuring a fresh install
The configuration will be based on my dotfiles at `github.com/shahzebs/dotfiles`.
