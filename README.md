# Viber for Void Linux

Make sure you read the comments in the template file.

## Why make a Viber xbps-src template?

I know there is the official AppImage and the unofficial Flatpak, but I just prefer to have one package manager and let that one handle everything.

## How do I build this package?

You just clone this repo or download it as a zip file, extract the content, copy/paste the `srcpkgs` directory in your `void-packages` directory, build it using xbps-src (`./xbps-src pkg viber`) and then install it with xbps-install (`sudo xbps-install --repository hostdir/binpkgs viber`).

## Why isn't this in the official repo?

Viber doesn't use version numbering. Basically, you really have no idea what version of Viber you're running (unless you check the binary). XBPS uses version numbering and revisions to decide whether a package needs updating or not. So, the maintainers wouldn't allow something like this in the official repo or in xbps-src.

## So, how am I supposed to update Viber?

You'd have to either up the version number (say, from 1.0.0 to 1.0.1) or the revision (from 1 to 2) in the template... or just uninstall Viber, repackage it and install it again.

## How do I know if Viber is out of date?

You don't... short of downloading the Debian package manually, unpacking it and checking the binary's version, there is no way of knowing. You use it till it stops connecting to the Viber network because it's really out of date and then update the template (you'll need a new SHA256 checksum, but xbps-src will provide that in an error when building the package, if the one in this template is not valid), repackage Viber again, use one of the methods described above to update the install and that is basically it.

Viber may also inform you that it's out of date (upper left corner I believe), but if it's still connecting to the Viber network and you really don't need any new feature it might have, I'd leave it be. Though, of course, the choice is yours.

## Why is the template x64 only?

Go bug Viber about that. They only provide native binaries for Ubuntu, which has dropped all 32-bit support, inlcuing x86.

License: WTFPL v3.1

<img src="http://www.wtfpl.net/wp-content/uploads/2012/12/wtfpl-badge-1.png">
