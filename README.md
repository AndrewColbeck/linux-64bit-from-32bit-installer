# How to install Linux 64-bit Distro on older 32-bit EFI booting Macs (tested with MacPro model 1,1)
The MacPro 1,1 along with other legacy models from around 2006 (the Core2Duo era) are capable of running 64-bit operating systems and applications, but were produced with a 32-bit EFI ROM.  This means the installation process requires conversion of an official ISO into 32-bit EFI compliant media.

## Instructions

### Boot Media Creation
- Download desired Linux ISO (**Note:** I've only had success  with Ubuntu 2̶0̶.̶0̶4̶.̶1̶ ̶L̶T̶S̶, 16.04.7 AMD 64Bit version)
- Verify the ISO with SHA256 checksum, see instructions [here](https://ubuntu.com/tutorials/how-to-verify-ubuntu#3-download-checksums-and-signatures)
- Download the enclosed `isomacprog.c` script
- Doublecheck the script, never run anything without doublechecking! ;)
- Compile the script: `cc -g -Wall isomacprog.c -o isomacprog`
- Make a copy of the ISO as a backup: `cp <original-iso-name>.iso macversion.iso`
- Run the compiled script against the *copy* of the ISO `./isomacprog macversion.iso` 
- Check terminal/console for errors, although only basic error handling is included.
- burn the `macversion.iso` to CD/DVD Disk Utility is fine: right click the macversion.iso file and click burn to disk

### Installation
- Boot your mac up, and insert the DVD
- Restart the mac and hold the 'option' key
- The boot media will be called 'Windows' and have a disk icon, click this to start the install
- When the boot loader asks 'what would you like to do?', identify the disk you want to install ubuntu on, and select 'erase entire disk'
- **IMPORTANT** In Device for boot loader installation, change this to match the same disk identifier as the Ubuntu disk (I.e. /dev/sdb)
- Click continue, and follow the remaining prompts.
- When wanting to boot up in Ubuntu, simply hold the `Option` key and select the Hard Drive labelled 'Windows'

##### Acknowledgements
<sup>Matt Gadient's Linux DVD images and how-to for 32-bit EFI Macs late 2006 models [link](https://mattgadient.com/linux-dvd-images-and-how-to-for-32-bit-efi-macs-late-2006-models/)<br>Thomas Schmitt: 64-bit to 32-bit ISO conversion script [link](https://bugs.launchpad.net/ubuntu-cdimage/+bug/1298894/comments/16)<sup>
