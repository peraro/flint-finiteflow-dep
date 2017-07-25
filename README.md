FLINT 2 for Ampff
=================

This is a very minimal version of the Flint library which contains all
the Flint dependencies of the Ampff library.  It is only intended for
Ampff users which do not wish to install the full Flint library.

Unlike the full Flint library, this version has no external
dependencies.

Installation
------------

This version of Flint uses the CMake build system.  It can be
installed with the following command

```
cmake -DCMAKE_INSTALL_PREFIX=/installation/path/prefix && make install
```

where the `-DCMAKE_INSTALL_PREFIX` can be omitted if for installation
in a default path.
