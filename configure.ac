# Tell autoconf we're compiling a C++ library, using automake & libtool
AC_INIT(adplug,2.3)
AC_CONFIG_SRCDIR(src/adplug.cpp)
AC_CONFIG_FILES([Makefile src/Makefile src/version.h doc/Makefile adplugdb/Makefile test/Makefile adplug.pc])
AM_INIT_AUTOMAKE
AM_MAINTAINER_MODE
#AM_DISABLE_SHARED
AM_PROG_LIBTOOL
AC_LANG(C++)

# Check for a sane C/C++ build environment.
AC_PROG_MAKE_SET
AC_PROG_INSTALL
AC_PROG_CC
AC_PROG_CXX

# Check for needed libraries.
AC_CHECK_LIB(stdc++,main,,AC_MSG_ERROR([libstdc++ not installed]))
PKG_CHECK_MODULES([libbinio], [libbinio >= 1.4])

# Check if getopt header is installed on this system
AC_CHECK_HEADERS([getopt.h], , AC_SUBST(GETOPT_SOURCES, [getopt.c getopt.h]))

# Sanitize some compiler features, which may be broken...
AC_C_CONST
AC_C_INLINE

# Enable debugging on user request.
AC_ARG_ENABLE([debug],AC_HELP_STRING([--enable-debug],
[Compile with debug logging support (default is to disable debug logging)]),
	AC_DEFINE(DEBUG))

AC_OUTPUT
