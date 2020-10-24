# How to install Linux 64-bit Distro on older 32-bit EFI booting Macs (tested with MacPro model 1,1)
The MacPro 1,1 along with other legacy models from around 2006 (the Core2Duo era) are capable of running 64-bit operating systems and applications, but were produced with a 32-bit EFI ROM.  This means the installation process requires conversion of an official ISO into 32-bit EFI compliant media.

## Instructions
- Download desired Linux ISO (**Note:** I have only tried this with Ubuntu Version 20.04.1 LTS.)
- Verify the ISO with SHA256 checksum, see instructions [here](https://ubuntu.com/tutorials/how-to-verify-ubuntu#3-download-checksums-and-signatures)
- Download enclosed the enclosed `isomacprog.c` script
- Doublecheck the script, never run anything without doublechecking! ;)
- Compile script: `cc -g -Wall isomacprog.c -o isomacprog`
- Make a copy of the ISO as a backup: `cp <original-iso-name>.iso macversion.iso`
- Run the compiled script against the *copy* of the ISO `./isomacprog macversion.iso` 
- Check terminal/console for errors, although only basic error handling is included.
- burn the `macversion.iso` to CD/DVD not Disk Utility: right click the macversion.iso file and click burn to disk
- Hold `Option` key while booting Mac, the boot media will like be called "Windows"
- Follow Ubuntu installer instructions

## Credit
Matt Gadient's Linux DVD images and how-to for 32-bit EFI Macs late 2006 models [link](https://mattgadient.com/linux-dvd-images-and-how-to-for-32-bit-efi-macs-late-2006-models/)

Thomas Schmitt: 64-bit to 32-bit ISO conversion script [link](https://bugs.launchpad.net/ubuntu-cdimage/+bug/1298894/comments/16)
