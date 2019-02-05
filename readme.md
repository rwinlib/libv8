#V8

V8 version 6.2.414.50 as included with node 8.11 LTS.

Built with msys2 because it requires python2. 
Just override the compiler path to rtools or rtools40 in the PKGBUILD.
I commented out 3 patches that did not work on GCC 4.9.3 (but the do work in rtools40)
