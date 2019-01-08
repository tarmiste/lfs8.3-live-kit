
# Notes

08Jan2019:

The live CD build scriptlets are mostly (but not entirely) consistent 
with the versions and build instructions from BLFS 8.3.   

The yaboot package (only for ppc) is packaged as a binary and provided in
the extrasources directory.   Building yaboot from source is dependent
on the versions of other packages (notably e2fsprogs).   yaboot source
has not been changed in some years and no longer builds from source with
the build environment in LFS8.3 (probably hasn't been buildable since LFS 7.5ish).
Due to build difficulties, the yaboot binary package in this kit was 
created by repacking the debian yaboot binary package into a 
simply tar archive which is then unpacked into the PPC live CD image.

The certs install in this kit was taken from BLFS 8.1.  Haven't been able
to get the certs from 8.3 working so reverted back to how it was done in
BLFS 8.1.




