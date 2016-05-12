This set of scripts is used in conjunction with VirtualBox to build an
Ubuntu 16.04 VM with a barebones desktop environment.

Prerequisites:
  * [VirtualBox 5.0.20+][1] installed
  * [Ubuntu 16.04 "mini" ISO][2]
  * [VirtualBox Guest Additions 5.0.16 ISO][3]

Start by creating a VM with specifications appropriate for your system,
then install Ubuntu 16.04 using the "mini" ISO. During package
selection, uncheck everything. When installation is complete, press the
button to complete installation and reboot, then eject the Ubuntu ISO
(you might have to force it).

When the system comes back up, log in using the user account you created
during the installation process. Use apt to install whatever you need to
obtain a copy of the vm-setup script. Run the script. Insert the Guest
Additions ISO when prompted.

Once vm-setup is finished, reboot. If you want Docker, run
vm-docker-setup when the system comes back up. It will add the official
Docker APT repo and install docker-engine.

On top of the Ubuntu base system, vm-setup installs the following:
  * VirtualBox Guest Additions
  * alsa-utils - required for sound to work
  * build-essential - required to build software
  * chromium-browser - web browser
  * feh - sets desktop background
  * git - required to clone dotfiles
  * i3 - tiling window manager
  * nodm - facilitates auto-login
  * psmisc - contains 'killall'
  * vim-gtk3 - editor
  * xorg - graphics

[1]: https://www.virtualbox.org/wiki/Downloads
[2]: http://archive.ubuntu.com/ubuntu/dists/xenial/main/installer-amd64/current/images/netboot/mini.iso
[3]: http://download.virtualbox.org/virtualbox/5.0.16/VBoxGuestAdditions_5.0.16.iso
