SUBDIRS = icons

gsettings_SCHEMAS = org.gnome.klotski.gschema.xml
@GSETTINGS_RULES@

man_MANS = gnome-klotski.6

pixmapdir = $(datadir)/gnome-klotski
pixmap_DATA = \
	gnome-klotski.svg

desktopdir = $(datadir)/applications
desktop_in_files = gnome-klotski.desktop.in
desktop_DATA = $(desktop_in_files:.desktop.in=.desktop)
@INTLTOOL_DESKTOP_RULE@

appdatadir = $(datadir)/appdata
appdata_in_files = gnome-klotski.appdata.xml.in
appdata_DATA = $(appdata_in_files:.xml.in=.xml)
@INTLTOOL_XML_RULE@

EXTRA_DIST = \
	$(appdata_in_files)	\
	$(gsettings_SCHEMAS)	\
	$(desktop_in_files)	\
	$(man_MANS)		\
	$(pixmap_DATA)

CLEANFILES = \
	$(appdata_DATA)	\
	$(desktop_DATA)

check-local: $(appdata_DATA) $(desktop_DATA)
	$(APPDATA_VALIDATE) $(appdata_DATA)
	$(DESKTOP_FILE_VALIDATE) $(desktop_DATA)

-include $(top_srcdir)/git.mk
