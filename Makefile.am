AUTOMAKE_OPTIONS = foreign dist-bzip2 1.6

AM_CPPFLAGS = $(all_includes) -I$(top_srcdir)/include
SUBDIRS = include src doc contrib tests

pkgconfigdir = $(libdir)/pkgconfig
pkgconfig_DATA = \
	libosmo-sbcap.pc \
	$(NULL)

EXTRA_DIST = .version \
	README.md \
	git-version-gen \
	contrib/osmo-cbc.spec.in \
	cbc.schema.json \
	smscb.schema.json \
	$(NULL)

AM_DISTCHECK_CONFIGURE_FLAGS = \
	--with-systemdsystemunitdir=$$dc_install_base/$(systemdsystemunitdir)

@RELMAKE@

BUILT_SOURCES = $(top_srcdir)/.version
$(top_srcdir)/.version:
	echo $(VERSION) > $@-t && mv $@-t $@
dist-hook:
	echo $(VERSION) > $(distdir)/.tarball-version
