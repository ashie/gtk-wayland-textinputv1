# -*- Mode: Makefile; tab-width: 8; indent-tabs-mode: t; -*-

AM_CPPFLAGS = \
	-Wall

if HAVE_GTK3
im_gtkwltextinputv1_LTLIBRARIES = im-gtkwltextinputv1.la
endif

im_gtkwltextinputv1dir = $(GTK3_IM_MODULEDIR)

im_gtkwltextinputv1_la_CFLAGS = \
	$(GTK3_CFLAGS)
im_gtkwltextinputv1_la_LDFLAGS = \
	-rpath $(im_gtkwltextinputv1dir) -avoid-version -module $(no_undefined)
im_gtkwltextinputv1_la_LIBADD = $(GTK3_LIBS)
im_gtkwltextinputv1_la_SOURCES = \
	gtkimcontextwayland.c gtkimcontextwayland.h \
	imwayland.c
