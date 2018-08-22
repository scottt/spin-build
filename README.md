spin-build
===

Build and install the [Spin](https://spinroot.com) model checker.
```
$ ./spin-build             # installs spin, modex and friends in $HOME/spin
$ ./spin-build /opt/spin   # installs in specified path
$ ./spin-clean             # clean sources extracted in current working directory
```

You'll need to have:
* `byacc`, `bison`, `flex`, `make`, `gcc` packages installed to build [Spin](http://spinroot.com/spin/Man/README.html#S1) and [Modex](http://spinroot.com/modex/).

You'll further need:
* `graphviz` and Tcl/Tk to run `ispin` and `tau`
 * `tau` needs GNU `awk` instead of the one shipped with MacOS (`brew install gawk`)
* a graphical Java environment to run `jspin`

## Rationale
* spin, modex and related utilities:
  * either don't have a toplevel directory in their tarballs or have one that doesn't match their tarball names
  * don't follow the standard `./configure --prefix`, `make`, `make install` convention of software packaging
* This script exists to saves new users some time
