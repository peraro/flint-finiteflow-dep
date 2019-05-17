FLINT 2 for FiniteFlow
======================

This is a very minimal version of the Flint library which contains all
the Flint dependencies of the
[FiniteFlow](https://github.com/peraro/finiteflow ) library.  It is
only intended for FiniteFlow users which do not wish to install the
full Flint library.

Unlike the full Flint library, this version only depends on the GMP
library.

The contents of the original README of Flint are in README_ORIGINAL.

For more information on the full Flint library, see
[http://www.flintlib.org/](http://www.flintlib.org/)


Installation
------------

This version of Flint uses the CMake build system, and it also depends
on the GMP library.  Both dependencies are often preinstalled or can
be easily installed using popular package managers on UNIX-like
systems.

This library can be installed with the following commands

```
cmake -DCMAKE_PREFIX_PATH=/gmp/installation/path/prefix \
      -DCMAKE_INSTALL_PREFIX=/installation/path/prefix .
make install
```

where the `-DCMAKE_INSTALL_PREFIX` option can be omitted for
installation in a default path, and the `-DCMAKE_PREFIX_PATH` is only
needed if GMP is not installed in a default path.
