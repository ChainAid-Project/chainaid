
Debian
====================
This directory contains files used to package chainaidd/chainaid-qt
for Debian-based Linux systems. If you compile chainaidd/chainaid-qt yourself, there are some useful files here.

## chainaid: URI support ##


chainaid-qt.desktop  (Gnome / Open Desktop)
To install:

	sudo desktop-file-install chainaid-qt.desktop
	sudo update-desktop-database

If you build yourself, you will either need to modify the paths in
the .desktop file or copy or symlink your chainaidqt binary to `/usr/bin`
and the `../../share/pixmaps/chainaid128.png` to `/usr/share/pixmaps`

chainaid-qt.protocol (KDE)

