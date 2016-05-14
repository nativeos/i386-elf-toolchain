# i386-elf-compiler-collection

* [About](#about)
* [Supported platforms](#supported-platforms)
* [Downloading precompiled packages](#downloading-precompiled-packages)
* [How to build](#how-to-build)

## About

This buildscript downloads, compiles and installs GNU Binutils and GNU GCC
targetting the i386-elf platform as a cross-compiler. It can be used to build
the i386-elf-binutils and i386-elf-gcc cross-compilers on different
architectures. A typical use case for this is people interested in operating
systems development.

## Supported platforms

The following platforms have been tested and are known to work:

* GNU/Linux - both i686 and x86_64.
* MacOS X - x86_64 (i686 is deprecated).
* Windows / MinGW - i686 (x86_64 is still not tested).

## Downloading precompiled packages

Please note that the building process can take several minutes depending on
the specs of your computer. On a relatively new computer it might take a few
minutes. On an older computer might take an hour or even more. Also, it has
been found that the build process is extremely slow in Windows due to the
MinGW emulation.

Several precompiled packages have been provided as is and are available at the
[releases](https://github.com/danirod/i386-elf-compiler-collection/releases)
page of this repository. Download a precompiled package for your architecture
and follow the installation instructions to get an usable environment.

## How to build

You can also build the compiler on your own if you prefer.

Your host computer needs to have the following software installed: **gcc**,
**g++**, **flex**, **bison**, **texinfo** and **wget**. Several libraries
required for building GCC such as **gmp**, **mpc** and **mpfr** are
download and precompiled by the script. They can be installed too to speed
up the build process.

**Note for Windows users**: you need to set up an usable UNIX environment
on your Windows system such as MingW or MSYS to run the buildscripts. Cygwin
has not been tested although I'm interested in.

Once your system is ready, clone the repository, download as ZIP or
get the script on any way and run it. Usage:

    ./buildcomp -p <prefix> [-l <log_file>] [-v]
        
Options:

* -p <prefix>: the script will install the compiler suite to <prefix>. This
  argument is required and the script has to be provided with a valid 
  directory: it has to exist and the script must be able to write to it.
  The script will refuse to work otherwise.
* -v: if provided, will print to the console the output of the build process
  (such as the output made by `make` and `configure`).
* -l <log_file>: if provided, will save the output of the build process to the
  log file with the name hereby given.
