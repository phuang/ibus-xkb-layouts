libexec_PROGRAMS = ibus-engine-xkb-layouts

ibus_engine_xkb_layouts_SOURCES = \
	main.c \
	engine.c \
	engine.h \
	xkbutil.c \
	xkbutil.h \
	gtkimcontextsimpleseqs.h \
	$(NULL)
ibus_engine_xkb_layouts_CPPFLAGS = \
	$(PREDEFINED_MACROS) \
	$(NULL)
ibus_engine_xkb_layouts_CFLAGS = \
	@IBUS_CFLAGS@ \
	$(NULL)
ibus_engine_xkb_layouts_LDFLAGS = \
	@IBUS_LIBS@ \
	$(NULL)

component_DATA = \
	xkb-layouts.xml \
	$(NULL)
componentdir = @datadir@/ibus/component

EXTRA_DIST = \
	xkb-layouts.xml.in \
	$(NULL)

CLEANFILES = \
	xkb-layouts.xml \
	$(NULL)

xkb-layouts.xml: xkb-layouts.xml.in
	$(AM_V_GEN) \
	( \
		libexecdir=${libexecdir}; \
		pkgdatadir=${pkgdatadir}; \
		s=`cat $<`; \
		eval "echo \"$${s}\""; \
	) > $@

# gtkimcontextsimpleseqs.h: compose-parse.py
# 	$(AM_V_GEN) \
# 	./compose-parse.py --gtk | sed 's/GDK_KEY_/IBUS_/g' > $@ || \
# 	( rm -rf $@ ; exit 1 )
