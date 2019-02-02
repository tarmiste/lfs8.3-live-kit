
## Creating a bootable live usb stick:

The live image can be written and booted from a usb flash drive rather than an CD/DVD.  

As always, prior to beginnging make sure that you back up anything of importance
on your system. 


### Intel machines:

#### Create:


Insert the usb drive in the machine and determine which device node cooresponnds
to your usb drive.   This will vary from system to system.

make sure unmounted.

dd if=.....iso of=/dev/sdX bs=512k


#### Boot:

Insert flash drive into machine and reboot.   Enter the bios or whatever screen and select boot from flash drive.



### PowerMac machines:


#### Create:

mac-fdisk.  i, b, c, c

hformat /dev/sdX2
hmount
h..
mount /dev/sdX3 /mnt/goo
vmlinux
mount /dev/sdXR /mnt/goo
cpio



#### Boot:

enter of
dev / ls
determine usb drive device path
boot usb1:\\yaboot
devicepath:3/vmlinux root=/dev/sdX4 ro rootdelay=10

