# Pre-compiled libyal libraries

These are binary files of [libyal libraries](https://github.com/libyal) which are compiled with Visual Studio 2019.

## What's the difference from original source code?

### libvshadow

I applied a patch for reading recovered catalog file and store file with [vss_carver](https://github.com/mnrkbys/vss_carver) to libvshadow.

The patch has been published on [my repository](https://github.com/mnrkbys/libvshadow-vss_carver).

### libvmdk

I applied a patch for supporting VMDK files which have encoding="Shift_JIS" to libvmdk. I mentioned it on my [tweet](https://twitter.com/unkn0wnbit/status/1235759995871997952). The patched libvmdk can read them without modifying VMDK.

The patch has been published on [my repository](https://github.com/mnrkbys/libvmdk-Shift_JIS).

### libewf and libewf-legacy

libewf and libewf-legacy were compiled without patches.

## When was the source code done git clone?

I did git clone on dates below:

- libvshadow: Mar. 10, 2020
- libvmdk: Mar. 9, 2020
- libewf: Mar. 9, 2020
- libewf-legacy: Mar. 11, 2020

## Compiling conditions

Using tools below for compiling.

- Visual Studio 2019
- Python 3.7.6
- Dokany 1.3.1
- zlib 1.2.11
- bzip2 1.0.6

## Installation

### Windows

```bash
git clone https://github.com/mnrkbys/precompiled_libyal_libs.git
```

If you want to use Python binding libraries (e.g. pyvmdk.pyd), you have to put \*.pyd, lib*.dll, and zlib.dll in <Python37_install_folder>\Lib\site-packages folder (pyewf.pyd needs bzip2.dll too).

### Linux/macOS

I recommend to compile them by yourself. Please follow the building instructions of their wiki page.

## bzip2.def

I am offering bzip2.def file in libewf directory. It's called "Module Definition File".

This file will be needed, if you compile libewf by yourself with Visual Studio. You have to set the path of bzip2.def below:

bzip2 Property -> Configuration Properties -> Linker -> Input -> Module Definition File

## Author

libyal: [Joachim Metz](https://github.com/joachimmetz)

zlib: [Jean-loup Gailly](jloup@gzip.org) and [Mark Adler](madler@alumni.caltech.edu)

bzip2: [Julian Seward](jseward@bzip.org)

## License

libyal libraries: [LGPLv3+](http://www.gnu.org/licenses/)

zlib: [zlib license](https://zlib.net/zlib_license.html)

bzip2: [BSD-like license](LICENSE_bzip2)
