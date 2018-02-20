# Octo86_for_Devuan_1.0.0
Automated Devuan-based OctoPrint installation for PC

  I've been using the popular "octopi" release of foosle's OctoPrint for a while.  Various factors prompted me to move to an Atom-based netbook to host Octoprint.  I didn't find sutiable distribution packages for either OctoPrint or mjpg-streamer, so I decided to just create an automated installation for the whole works.

  These scripts are based on Devuan's NETINST installation images.  They modify the stock ISO to provide options to install Octoprint as a system service.  The resulting bootable ISO image can be burned to CD or DVD or dd'ed to a USB flash drive.

  Both OctoPrint and mjpg-streamer are downloaded and installed unmodified on your target computer.  They are not downloaded or installed on the system used to build the image.
  
  https://github.com/foosel/OctoPrint
  
  https://github.com/jacksonliam/mjpg-streamer
  
  Check http://devuan.org for Devuan's licensing information and the above links for license terms for OctoPrint and mjpg-streamer.  My work is licensed under the Creative Commons Attribution terms.
  
  This code has been tested for i386 and amd64 target architectures on Devuan v1.0.0 (jessie).  It is very simple, easily broken, and requires at least basic Linux skills.
  
Target hardware requirements:
x86 based CPU - 1.5GHz recommended
1GB RAM - bare minimum for good 3D prints while using the streaming video feature
2GB storage - Tested on a 2GB Disk On Module.  Will NOT install in 1GB.
  
  IMPORTANT NOTE:
  The whole point of this code is to automatically overwrite whatever is on the system that boots the resulting image.  If you boot from the created image and choose any OctoPrint "AutoInstall" option, you WILL overwrite and destroy all data on that system's primary drive.  Use it at your own risk.  I can't be responsible for lost data.

  
  To make your ISO:
  You'll need a running Devuan or Debian system with about 600MB disk space available, and with bash, isolinux, xorriso, and bsdtar installed.  Other distributions and UNIXs may work but I haven't tested them.

1) Download the repository as a ZIP file. Unzip the file with the "-X" option and CD into the new directory For example:

   $ unzip -X Octo86-master && cd Octo86-master/

2) Read the included README files.  This is important!
3) Download or copy the Devuan v1.0.0 NETINST ISO file into the directory.  DO NOT CHANGE THE NAME OF THE ISO FILE!  The setup script depends on the ISO name as set by Devuan.
4) Run the TWIDDLE script:

   $ ./TWIDDLE <arch> <subdir>
  
  where <arch> is i386 or amd64, depending on the ISO you have.  The <subdir> argument names the working directory where the image is unpacked.
5)  The script should unpack the ISO, add the necessary files to the archive, modify the boot menu, and write a bootable image.
6)  Write the new ISO to your media, boot the target system - the computer that will run OctoPrint - and follow the directions in the README.


Comments, suggestions, and expecially bug reports are welcome.
