## Notes about compiling package

You will need to move these files to `name-of-custom-folder/debian` to compile this.

To compile:
* Copy all ported edition files to the `name-of-custom-folder` excluding folders. If files are in folders, like `foo/foo_xyz.png` then move the files out of the folder and remove the folder once empty.
* Change directory to `name-of-custom-folder` and enter root terminal via `sudo su`
* `dpkg-buildpackage -rfakeroot -b -uc` to build the binary or `dpkg-buildpackage -rfakeroot -b -us -uc` to build the binary and source. Note: the `.changes` file will not upload to Launchpad.net because `dpkg-buildpackage` does not access gpg key and sign the `.changes` or `.dsc` files.
* Lintian is very sensitive and will throw up errors and warnings. Just ignore them unless they have anything to do with `debian/rules`, `debian/control`, or `debian/changelog`. In which case, <a href="https://github.com/SparrOSDeveloperTeam-Win/SYGTVG-REL/issues">tell us</a>.
