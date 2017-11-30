
Debian
====================
This directory contains files used to package luxd/lux-qt
for Debian-based Linux systems. If you compile luxd/lux-qt yourself, there are some useful files here.

## lux: URI support ##


lux-qt.desktop  (Gnome / Open Desktop)
To install:

	sudo desktop-file-install lux-qt.desktop
	sudo update-desktop-database

If you build yourself, you will either need to modify the paths in
the .desktop file or copy or symlink your lux-qt binary to `/usr/bin`
and the `../../share/pixmaps/bitcoin128.png` to `/usr/share/pixmaps`

lux-qt.protocol (KDE)

