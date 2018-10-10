
Debian
====================
This directory contains files used to package Mongerd/Monger-qt
for Debian-based Linux systems. If you compile Mongerd/Monger-qt yourself, there are some useful files here.

## Monger: URI support ##


Monger-qt.desktop  (Gnome / Open Desktop)
To install:

	sudo desktop-file-install Monger-qt.desktop
	sudo update-desktop-database

If you build yourself, you will either need to modify the paths in
the .desktop file or copy or symlink your Mongerqt binary to `/usr/bin`
and the `../../share/pixmaps/Monger128.png` to `/usr/share/pixmaps`

Monger-qt.protocol (KDE)

