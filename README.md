# Viber_Fix
Fix Viber on Ubuntu 18.04 and based distros

## How to fix it

To fix Viber on Ubuntu and base distros you should:

1. Download viber from [Viber Website](https://www.viber.com/download/)
2. Run:

```
$ dpkg-deb -x viber.deb viber
$ dpkg-deb --control viber.deb viber/DEBIAN
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
$ dpkg -b viber vibernew.deb
$ sudo dpkg -i vibernew.deb
```
By now Viber should be working.