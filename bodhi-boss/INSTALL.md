# Installation and Usage

Naturally, Bodhi Linux users can install this theme from the repos, see below.

For all other distros, to install and use this theme one call follow these three steps:

* Git clone this repository.

* Copy the directory corresponding to the desired Plymouth Theme into the System's Plymouth themes directory. Super user privileges will be required.

* As root set Plymouth's Default theme and  Update initramfs.

**NOTE:** the specific steps may vary depending on your distro.


# Installation on Bodhi Linux 6.x or greater

```bash
sudo apt update
sudo apt install plymouth-theme-bodhi-boss
```

# Installation on Ubuntu based distros

**Either download Bodhi's deb file and install it:**

```bash
wget http://packages.bodhilinux.com/bodhi/pool/b7main/p/plymouth-theme-bodhi-boss/plymouth-theme-bodhi-boss_0.0.1-1_all.deb
sudo apt install ./plymouth-theme-bodhi-boss_0.0.1-1_all.deb
```

**Or manually install:**

First be sure git and meson are installed. Then:

```bash
git clone https://github.com/BodhiDev/bodhi-plymouth-themes
cd bodhi-plymouth-themes/bodhi-boss
meson . build
sudo ninja -C build install
sudo update-alternatives --install /usr/share/plymouth/themes/default.plymouth default.plymouth /usr/share/plymouth/themes/bodhi-boss/bodhi-boss.plymouth 10
update-initramfs -u
```

**NOTE:** This method of manually installation should work in any distro which installs Plymouth Themes to `/usr/share/plymouth/themes/` and uses `update-alternatives` to manage plymouth themes.

# Installation on other distros

For oher Distros, consult your distros documention.

# To use the theme

For Bodhi and all other Ubuntu based distros, to select this theme and Plymouth's Default theme and  Update initramfs.

### Select the Theme and Update initramfs
```
sudo update-alternatives --config default.plymouth
```
Choose the index of the Bodhi Boss theme. Then run:
```
sudo update-initramfs -u
```
Reboot to see the theme in action.

**NOTE:** This above commands should work in any distro which installs Plymouth Themes to `/usr/share/plymouth/themes/` and uses `update-alternatives` to manage plymouth themes.


### For all other distros

```
sudo plymouth-set-default-theme -l
```

This will print a list of themes that are present in the default plymouth theme directory. To choose a one:

```
sudo plymouth-set-default-theme -R THEME
```

Where THEME refers to one of the listed values from the executed command.
