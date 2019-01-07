# lfs8.3-live-kit

This repository contains material that is useful for creating a 
live (e.g. live CD) image of the LFS 8.3 release.

These materials consist of package build scriplets, 
kernel configuration files, patches, shell scripts, README files
and other materials that are helpful in creating a LFS live CD.

This project is not a continuation of the (now defunct) LFS live
CD project that previously existed as part of the LFS project.  This 
project is a new approach to building a LFS live CD and is not
endorsed nor sponsored by the mainline LFS project.  So, don't 
ask for support or raise issues about this project on the LFS 
mailing lists.

## Goals

1) Provide a semi-automated build of a LFS live CD.  (Several
   user interactive steps will be needed to build a live CD.)
   This project does not provide a fully automated, push a button,
   kind of live CD build.

2) Low maintenance.  Should be easy to port to new versions of
   LFS as they are released.  The contents of the live CD will
   be what is required to build LFS on a target system and not
   much more than that.  Minimizing the packages on the live CD
   will minimize the maintenance required and effort needed to
   adapt it to future LFS releases.

3) Customizable.  The live CD build should be customizable by 
   the user to suit their own needs.  

4) The live CD should provide the tools needed to build LFS 8.3 and
   utilize the blfs tool in the resulting LFS 8.3 system.   It is 
   nice (but not required) if the live CD also supports building
   other releases within a couple of revs of 8.3 (i.e. 8.1 to 8.4). 

5) The ability to build CLFS 3.0.0 with the live CD is desirable but
   not a firm goal of this project.

6) The 'live CD' image should also be bootable via USB flash drive.

7) Targeted machines: x86_64, i686, PowerMACs (32 and 64 bit).

## Overview of live CD build process

   More details are provided in the various README files but a high 
   level view of the live CD build process is:

1) Obtain the contents of this lfs8.3-live-kit and cd into it.

2) Run the script "./lfslive_prep.sh".   It creates and populates 
   a couple of directorys (~HOME/lfs83live_host and /mnt/lfs83live_target).

3) cd to the (newly created) ~HOME/lfs83live_host directory/jhalfs

4) Run make and configure jhalfs to build LFS8.3, custom tools and the
   kernel.  Let it run and after some hours (or days for slow machines)
   the live CD root file system will have been created in the 
   /mnt/lfs83live_target directory.

5) Set 'export LFS=/mnt/lfs83live_target' and then run 3 shell scripts
   which squash the live rootfs and package it into a bootable CD ISO
   image.


## Repository contents:

lfslive_prep.sh:  Script to kick off the process.

custom_configs:  Build scriptlets for live CD packages.

custom_ppc_configs:  Build scriptlets for PowerPC specific live CD packages.

extrasource:  Needed patches and files that are difficult to auto download.

extras: Copies of jhalfs, LFS and BLFS books.

kernel: Kernel .config files for building the live CD kernel.

READMEs and other documentation.

