#                                               -*- Autoconf -*-
# Process this file with autoconf to produce a configure script.

dnl Process this file with autoconf to produce a configure script.
m4_define([gtk_wltextinputv1_major_version], [0])
m4_define([gtk_wltextinputv1_minor_version], [0])
m4_define([gtk_wltextinputv1_micro_version], [1])
m4_define([gtk_wltextinputv1_version],
    gtk_wltextinputv1_major_version.gtk_wltextinputv1_minor_version.gtk_wltextinputv1_micro_version)

AC_INIT([gtk_wltextinputv1],
        [gtk_wltextinputv1_version],
        [https://github.com/ashie/gtk-wayland-textinputv1/issues],
        [gtk_wltextinputv1])
AC_CONFIG_HEADER([config.h])
AM_INIT_AUTOMAKE([1.11])
AM_SILENT_RULES([yes])


dnl
dnl Checks for programs.
dnl
AC_LANG([C])
AC_PROG_CC
AC_PROG_AWK
AC_PROG_INSTALL
AC_PROG_LN_S
AC_PROG_MAKE_SET


dnl
dnl Checks for host
dnl
AC_CANONICAL_HOST


dnl
dnl libtool
dnl
AC_ENABLE_SHARED(yes)
AC_ENABLE_STATIC(no)
AM_PROG_LIBTOOL


dnl
dnl Checks for gtk
dnl
GTK3_REQUIRED=3.0.0
PKG_CHECK_MODULES(GTK3, gtk+-3.0 >= GTK3_REQUIRED,
                  [have_gtk3=yes], [have_gtk3=no])
AM_CONDITIONAL(HAVE_GTK3, test $have_gtk3 = "yes")
if test $have_gtk3 = "yes"; then
    gtk3_binary_version=`$PKG_CONFIG --variable=gtk_binary_version gtk+-3.0`
    gtk3_libdir=`$PKG_CONFIG --variable=libdir gtk+-3.0`
    GTK3_IM_MODULEDIR="$gtk3_libdir"/gtk-3.0/$gtk3_binary_version/immodules
    AC_SUBST(GTK3_IM_MODULEDIR)
fi


dnl
dnl Checks for header files.
dnl
AC_HEADER_STDC
AC_CHECK_HEADERS([string.h])


dnl
dnl Checks for typedefs, structures, and compiler characteristics.
dnl


dnl
dnl Checks for library functions.
dnl


dnl
dnl Options to enable some features
dnl


AC_CONFIG_FILES([
Makefile
src/Makefile
])

AC_OUTPUT

AC_MSG_RESULT([
Configure result:

  GTK+3: ${have_gtk3}
])
