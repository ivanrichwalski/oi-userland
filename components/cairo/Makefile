#
# This file and its contents are supplied under the terms of the
# Common Development and Distribution License ("CDDL"), version 1.0.
# You may only use this file in accordance with the terms of version
# 1.0 of the CDDL.
#
# A full copy of the text of the CDDL should have accompanied this
# source.  A copy of the CDDL is also available via the Internet at
# http://www.illumos.org/license/CDDL.
#

#
# Copyright 2015 Alexander Pyhalov
#

include ../../make-rules/shared-macros.mk

COMPONENT_NAME= cairo
COMPONENT_VERSION= 1.14.2
COMPONENT_SUMMARY= Vector graphics library
COMPONENT_SRC= $(COMPONENT_NAME)-$(COMPONENT_VERSION)
COMPONENT_ARCHIVE= $(COMPONENT_SRC).tar.xz
COMPONENT_ARCHIVE_HASH= \
  sha256:c919d999ddb1bbbecd4bbe65299ca2abd2079c7e13d224577895afa7005ecceb
COMPONENT_ARCHIVE_URL= \
  http://cairographics.org/releases/$(COMPONENT_ARCHIVE)
COMPONENT_PROJECT_URL = http://cairographics.org/
COMPONENT_FMRI= library/desktop/cairo
COMPONENT_CLASSIFICATION= Desktop (GNOME)/Libraries
COMPONENT_LICENSE = LGPLv2.1
COMPONENT_LICENSE_FILE = COPYING-LGPL-2.1

include ../../make-rules/prep.mk
include ../../make-rules/configure.mk
include ../../make-rules/ips.mk

PATH=/usr/gnu/bin:/usr/bin

COMPONENT_PREP_ACTION =	( cd $(@D) && libtoolize --force --copy&&\
					aclocal  -I build && \
					gtkdocize &&\
                                        autoheader &&\
                                        automake -a -f -c --gnu &&\
                                        autoconf )

COMPONENT_PRE_CONFIGURE_ACTION = ( cp -a $(SOURCE_DIR)/* $(@D))

CONFIGURE_SCRIPT = $(@D)/configure

CFLAGS += -D_POSIX_PTHREAD_SEMANTICS

CONFIGURE_OPTIONS += --disable-static
CONFIGURE_OPTIONS += --enable-gl=yes
CONFIGURE_OPTIONS += --enable-xlib-xcb
CONFIGURE_OPTIONS += --enable-xml
CONFIGURE_OPTIONS += --enable-test-surfaces

build: $(BUILD_32_and_64)

install: $(INSTALL_32_and_64)

test: $(TEST_32_and_64)
