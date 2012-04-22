#                                               -*- Autoconf -*-
# Process this file with autoconf to produce a configure script.

AC_PREREQ([2.68])
AC_INIT([libandor], [3.4.30004.0], [softwaresupport@andor.com])
AM_INIT_AUTOMAKE
AC_CONFIG_SRCDIR([inc/atcore.h])
AC_CONFIG_HEADERS([config.h])

# Checks for programs.
AC_PROG_AWK
AC_PROG_CXX
AC_PROG_CC
AC_PROG_INSTALL
AC_PROG_LN_S
AC_PROG_MAKE_SET
LT_INIT

# Checks for libraries.

## Andor binary libraries
AC_CANONICAL_HOST
AC_MSG_CHECKING([for compatible pre-built binary libraries for host system])
HOST_ARCH="unknown"
case $host in
	i*86-*-*) HOST_ARCH="x86" ;;
	x86_64-*-*) HOST_ARCH="x86_64" ;;
esac
AC_MSG_RESULT($HOST_ARCH)
if test $HOST_ARCH = unknown ; then
	AC_MSG_ERROR([$PACKAGE has not been ported to $host])
fi
AC_SUBST(HOST_ARCH)

## USB args
AC_MSG_CHECKING([whether to install USB udev rules])
AC_ARG_ENABLE(
	[usb_udev],
	[AS_HELP_STRING(
		[--enable-usb_udev],
		[use USB connector to update camera firmware. \
		 Default = enabled])],
	[usb_udev="$enableval"],
	[usb_udev="yes"])
AM_CONDITIONAL([USB_UDEV], [test "$usb_udev" = yes])
AC_MSG_RESULT($usb_udev)
AC_MSG_CHECKING([whether to install USB hotplug scripts])
AC_ARG_ENABLE(
	[usb_hotplug],
	[AS_HELP_STRING(
		[--enable-usb_hotplug],
		[use USB connector to update camera firmware. \
		 Use the modern --enable-usb_udev instead if available. \
		 Default = disabled])],
	[usb_hotplug="$enableval"],
	[usb_hotplug="no"])
AM_CONDITIONAL([USB_HOTPLUG], [test "$usb_hotplug" = yes])
AC_MSG_RESULT($usb_hotplug)

# Checks for header files.
AC_CHECK_HEADERS([stdlib.h string.h sys/time.h sys/timeb.h unistd.h])

# Checks for typedefs, structures, and compiler characteristics.
AC_HEADER_STDBOOL
AC_TYPE_OFF_T
AC_TYPE_SIZE_T

# Checks for library functions.
AC_CHECK_FUNCS([ftime memset select])

AC_CONFIG_FILES([
	Makefile
	x86/Makefile
	x86_64/Makefile
])
AC_OUTPUT
