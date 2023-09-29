AM_CPPFLAGS = \
	-I$(top_srcdir) \
	-DG_LOG_DOMAIN=\"libprotocols\" \
	$(PLATFORM_CPPFLAGS)

noinst_LTLIBRARIES = \
	libprotocols.la

libprotocols_built_sources = \
	wlr-data-control-unstable-v1.c \
	wlr-data-control-unstable-v1-client.h

libprotocols_la_SOURCES = \
	wlr-data-control-unstable-v1.c

libprotocols_la_CFLAGS = \
	$(WAYLAND_CLIENT_CFLAGS) \
	$(PLATFORM_CFLAGS)

libprotocols_la_LDFLAGS = \
	-no-undefined \
	$(PLATFORM_LDFLAGS)

libprotocols_la_LIBADD = \
	$(WAYLAND_CLIENT_LIBS)

%.c: %.xml
	$(AM_V_GEN) wayland-scanner private-code $< $@

%-client.h: %.xml
	$(AM_V_GEN) wayland-scanner client-header $< $@

DISTCLEANFILES = \
	$(libprotocols_built_sources)

BUILT_SOURCES = \
	$(libprotocols_built_sources)

EXTRA_DIST = \
	wlr-data-control-unstable-v1.xml