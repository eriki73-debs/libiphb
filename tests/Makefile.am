#
# Generic options
#
AM_CFLAGS = -Wall -Wextra -Wmissing-prototypes -std=c99 -Os -g -fPIC
AM_CPPFLAGS = -D_GNU_SOURCE -I $(top_srcdir)
AM_LDFLAGS = -g -lrt -Wl,--as-needed

ACLOCAL_AMFLAGS = -I m4

#
# Additional dirs
#
testbindir = /opt/tests/libiphb-tests/bin

#
# Build targets
#
testbin_PROGRAMS = hbtest hbtest2 hbtest3
 
hbtest_SOURCES = hbtest.c
hbtest_LDADD = $(top_builddir)/src/libiphb.la

hbtest2_SOURCES = hbtest2.c
hbtest2_LDADD = $(top_builddir)/src/libiphb.la

hbtest3_SOURCES = hbtest3.c
hbtest3_CFLAGS  = $(AM_CFLAGS) $(GLIB_CFLAGS) $(DBUS_CFLAGS) #$(MCE_CFLAGS)
hbtest3_LDADD   = ../src/libiphb.la $(DBUSGLIB_LIBS) \
			$(top_builddir)/dbus-gmain/libdbus-gmain.la


#
# Install data
#
install-data-local:
	install -d $(DESTDIR)/opt/tests/libiphb-tests
	install -m 644 ./tests.xml $(DESTDIR)/opt/tests/libiphb-tests
