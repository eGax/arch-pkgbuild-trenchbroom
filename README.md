The purpose of this is to enable Arch users to install the past official release of TrenchBroom, version 2023.1. The way the AUR does, but I highly recommend you use the current TrenchBroom version at this time 2024.1.<br>

To install TB in your Arch distro of choice from a terminal :

`git clone https://github.com/eGax/arch-pkgbuild-trenchbroom.git`<br>
`cd arch-pkgbuild-trenchbroom`<br>
`makepkg -si`<br>


That will clone it, enter it, look for the required libtinyxml2.so.9, if not found then create a symlink from current `/usr/lib/libtinyxml2.so.10.0.0` to `/usr/lib/libtinyxml2.so.9`, then installs the package into your system.<br>
<br>
<br>
If you want to use the current release build of TrenchBroom 2024.1, highly recommend using my AUR trenchbroom-bit https://aur.archlinux.org/packages/trenchbroom-bin<br><br>

<i>** If this breaks, its a very low priority to fix it since it is an out of date version, but you can create a issue and I will look into when I can. **</i>
