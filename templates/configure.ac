dnl ##
dnl ## Process this file with autoconf to produce a configure script.
dnl ## 
AC_PREREQ(2.68)
LT_PREREQ([2.4.2])
AC_INIT([{{PackageName}}], m4_esyscmd([tr -d '\n' < VERSION]))
AC_CONFIG_SRCDIR([src/{{PackageName}}.c])
AC_CONFIG_HEADER([src/pkgconfig.h:cnf/pkgconfig.h.in])
AC_CONFIG_MACRO_DIR([m4])
AC_CONFIG_AUX_DIR([cnf])
AM_INIT_AUTOMAKE([1.11 -Wall foreign subdir-objects])
AM_SILENT_RULES([yes])
AM_MAINTAINER_MODE

dnl ##
dnl ## C is the language 
dnl ##
AC_PROG_CC
AC_LANG([C])

dnl ##
dnl ## setup libtool (for building the GAP kernel extension)
dnl ##
AM_PROG_AR
LT_INIT([disable-static dlopen win32-dll])

dnl ##
dnl ## Locate the GAP root dir
dnl ##
AC_FIND_GAP

dnl ##
dnl ## Detect pointer size to distinguish 32 and 64 bit builds
dnl ##
AC_CHECK_SIZEOF([void **])

dnl ##
dnl ## Detect Windows resp. Cygwin
dnl ##
AC_CYGWIN
AM_CONDITIONAL([SYS_IS_CYGWIN], [test "$CYGWIN" = "yes"])
if test "$CYGWIN" = "yes"; then
  AC_DEFINE(SYS_IS_CYGWIN32, 1, are we on CYGWIN?)
else
  AC_DEFINE(SYS_IS_CYGWIN32, 0, are we on CYGWIN?)
fi
     

AC_CONFIG_FILES([Makefile])
AC_OUTPUT