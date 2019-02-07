# V8

V8 version 6.2.414.50 as included with node 8.11 LTS.

Built with msys2 because it requires python2. 
Override the compiler path to rtools or rtools40 in the PKGBUILD. For tools40:

```
  export CPPFLAGS="-I${MINGW_PREFIX}/include"
  export CC="/C/rtools40${MINGW_PREFIX}/bin/gcc $CPPFLAGS"
  export CXX="/C/rtools40${MINGW_PREFIX}/bin/g++ -std=gnu++11 $CPPFLAGS"
  export PATH="/C/rtools40${MINGW_PREFIX}/bin:$PATH"
  export LIBS="-L${MINGW_PREFIX}/libs"
```

And for old rtools:

```
  export CPPFLAGS="-I${MINGW_PREFIX}/include"
  export CC="/C/Rtools${MINGW_PREFIX/mingw/mingw_}/bin/gcc $CPPFLAGS"
  export CXX="/C/Rtools${MINGW_PREFIX/mingw/mingw_}/bin/g++ -std=gnu++11 $CPPFLAGS"
  export PATH="/C/Rtools${MINGW_PREFIX/mingw/mingw_}/bin:$PATH"
  export LIBS="-L${MINGW_PREFIX}/libs"
```

For GCC 4.9.3 I commented out 3 patches that did not work. Uncomment those lines
for building with rtools40.

Update: also added a patch that reverts a Windows 7 API (for the CRAN builder).
We can remove that patch when CRAN upgrades the build server.
