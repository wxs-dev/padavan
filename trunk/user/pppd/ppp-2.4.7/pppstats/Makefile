#
# pppstats makefile
# $Id: Makefile.linux,v 1.9 2006/06/04 05:07:46 paulus Exp $
#
DESTDIR = $(INSTROOT)/usr
BINDIR = $(DESTDIR)/sbin
MANDIR = $(DESTDIR)/share/man/man8

PPPSTATSRCS = pppstats.c
PPPSTATOBJS = pppstats.o

#CC = gcc
COPTS = -O
COMPILE_FLAGS = -I../include
LIBS =

INSTALL= install

CFLAGS += $(COPTS) $(COMPILE_FLAGS)

all: pppstats

install: pppstats
	-mkdir -p $(MANDIR)
	$(INSTALL) pppstats $(BINDIR)
	$(INSTALL) -c -m 444 pppstats.8 $(MANDIR)

pppstats: $(PPPSTATSRCS)
	$(CC) $(CFLAGS) -o pppstats pppstats.c $(LIBS)

clean:
	rm -f pppstats *~ #* core

depend:
	cpp -M $(CFLAGS) $(PPPSTATSRCS) >.depend
#	makedepend $(CFLAGS) $(PPPSTATSRCS)
