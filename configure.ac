AC_PREREQ([2.63])
AC_INIT([GNOME Klotski], [3.13.90], [https://bugzilla.gnome.org/],
        [gnome-klotski], [https://wiki.gnome.org/Apps/Klotski])
AM_INIT_AUTOMAKE([1.11 no-dist-gzip dist-xz foreign])
AM_SILENT_RULES([yes])
AM_MAINTAINER_MODE
GNOME_MAINTAINER_MODE_DEFINES

AM_PROG_VALAC([0.16.0])
AM_PROG_CC_C_O

GLIB_GSETTINGS

dnl ###########################################################################
dnl Dependencies
dnl ###########################################################################

GLIB_REQUIRED=2.40.0
GTK_REQUIRED=3.10.0
RSVG_REQUIRED=2.32.0

PKG_CHECK_MODULES(GNOME_KLOTSKI, [
  glib-2.0 >= $GLIB_REQUIRED
  gtk+-3.0 >= $GTK_REQUIRED
  librsvg-2.0 >= $RSVG_REQUIRED
])

AC_PATH_PROG([APPDATA_VALIDATE], [appdata-validate], [/bin/true])
AC_PATH_PROG([DESKTOP_FILE_VALIDATE], [desktop-file-validate], [/bin/true])

dnl ###########################################################################
dnl Internationalization
dnl ###########################################################################

IT_PROG_INTLTOOL([0.50])
AC_SUBST(GETTEXT_PACKAGE, gnome-klotski)

dnl ###########################################################################
dnl Documentation
dnl ###########################################################################

YELP_HELP_INIT

dnl ###########################################################################
dnl Files to generate
dnl ###########################################################################

AC_CONFIG_FILES([
Makefile
po/Makefile.in
data/Makefile
data/icons/Makefile
data/icons/hicolor/Makefile
data/icons/HighContrast/Makefile
help/Makefile
src/Makefile
])
AC_OUTPUT
