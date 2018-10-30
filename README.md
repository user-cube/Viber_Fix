# Viber_Fix
Fix Viber on Ubuntu 18.04 and Ubuntu 18.04 based distros

## Installing

You can install Viber using:
```
$ sudo dpkg -i viber_ubuntu.deb
```
If fails run:
```
$ sudo apt install -f
$ sudo dpkg -i viber_ubuntu.deb
```
You can also do it manually using "Manual Installing" section.
## Manual Installing

To fix Viber on Ubuntu 18.04 and Ubuntu 18.04 based distros you should:

1. Download viber from [Viber Website](https://www.viber.com/download/)
2. Run:

```
$ sudo dpkg-deb -x viber.deb viber
$ sudo dpkg-deb --control viber.deb viber/DEBIAN
```
Then edit viber/DEBIAN/control and replace the content for:
```
Package: viber
Version: 7.0.0.1035
Section: non-free/net
Priority: extra
Architecture: amd64
Depends: libxss1, libssl1.0.0, libpulse0, libasound2, libnss3, libxcomposite1, libxcursor1, libxdamage1, libcurl4, libgstreamer-plugins-base1.0-0, libgstreamer1.0-0, gstreamer1.0-plugins-base, gstreamer1.0-plugins-good, gstreamer1.0-plugins-ugly, gstreamer1.0-pulseaudio, gstreamer1.0-libav
Installed-Size: 421336
Conflicts: Viber (<< 7.0.0.1035)
Replaces: Viber (<< 7.0.0.1035)
Maintainer: Viber Media Inc <support@viber.com>
Homepage: http://viber.com
Description: Free Text & Calls.
```
After that run:
```
$ sudo dpkg -b viber vibernew.deb
$ sudo dpkg -i vibernew.deb
```
By now Viber should be working.
