Utilities to modify Elf binaries to work with PaX hardened kernel.
There are several utilities in here, to help you navigate:

Directories src/ scripts/ doc/ test/ are integral parts of the elfix package.
These are distributed as one source tarball with `make dist` run in the top
diretory.
* paxctl-ng - C utility for doing XT_PAX and/or PT_PAX markings.
* pypaxctl - python utility for doing XT_PAX and/or PT_PAX markings.  Depends on pax.so.
* migrate-pax - python utility for migrating from XT_PAX flags to PT_PAX.  Depends on pax.so.
* revdep-pax - python utility for mapping ELF libraries to/from the ELF objects that link
  against them and migrating PAX flags between them.  Depends on pax.so.
* paxmark.sh - Bash script that does intelligent pax-marking like the pax-utils.eclass.
* paxmodule.c - C code for python module pax.so

Directories under misc/ are independant packages from one another and from the
elfix package.  They are NOT distributed with elfix when running `make dist` in
the top directory.  Each directory supplies its own build system.
* install-xattr - C wrapper to coreutils' install which preserves file system extended attributes.
* fix-gnustack - query or clear any ELF GNU_STACK executable flag

Directory pocs/ - Very experimental stuff.
* change-interp - C utility to the dynamic linker, INTERP as reported by `readelf -l`.
* eclass - a local copy of the pax-utils.eclass
* elf-manipulate - some dirty utilities to
* * clear-dt-path.c - remove RPATH and RUNPATH
* * parse-elf.c - print out the ELF header, sections headers and program headers.
* * print-sections.c - print out the contents of the section headers
* * remove-ptpax.c - change a PT_PAX_FLAGS phdr to PT_NULL
* ldd - python script to reproduce ldd's output using pyelftools
* link-maps - use VDB information to produce a full linkage map of the system
* mangle-paxflags - printout old EI_PAX flags and PT_PAX flags
* paxmark-libs - test how PAX flags migrate from libraries and plugins to their consumers
* revdep-pax-ng - same as revdep-pax but using information obtained from `ldd` and
  not VDB information.

## Build Status
[![Repoman Status](https://travis-ci.org/gentoo/elfix.png)](https://travis-ci.org/gentoo/elfix)
