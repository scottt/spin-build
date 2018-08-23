spin-build
===

Build and install the [Spin](https://spinroot.com) model checker.
```
$ ./spin-build             # installs spin, modex and friends in $HOME/spin
$ ./spin-build /opt/spin   # installs in specified path
$ ./spin-clean             # clean sources extracted in current working directory
```
This script itself requires [Python 3](PYTHON3-INSTALLATION.md) to run.

Sample Session:
```
$ git clone https://github.com/scottt/spin-build
$ cd spin-build
$ ./spin-build

(...)

spin-build: installed spin, ispin, jspin, modex, and tau in /home/scottt/spin

Add this to your .bashrc or equivalent:
  source /home/scottt/spin/spin.env

$ source $HOME/spin.env
$ printf 'init { printf("hello\\n") }' > hello.pml
$ spin hello.pml 
      hello
1 process created
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
