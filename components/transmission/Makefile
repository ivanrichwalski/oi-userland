#
# This file and its contents are supplied under the terms of the
# Common Development and Distribution License ("CDDL)". You may
# only use this file in accordance with the terms of the CDDL.
#
# A full copy of the text of the CDDL should have accompanied this
# source. A copy of the CDDL is also available via the Internet at
# http://www.illumos.org/license/CDDL.
#

#
# Copyright 2015 Alexander Pyhalov
#

include ../../make-rules/shared-macros.mk

COMPONENT_NAME=		transmission
COMPONENT_VERSION=	2.52
COMPONENT_PROJECT_URL=	http://www.transmissionbt.com/
COMPONENT_SUMMARY=	GTK and console BitTorrent client
COMPONENT_FMRI=		desktop/torrent/transmission
COMPONENT_CLASSIFICATION=	Applications/Internet
COMPONENT_SRC=		$(COMPONENT_NAME)-$(COMPONENT_VERSION)
COMPONENT_ARCHIVE=	$(COMPONENT_SRC).tar.bz2
COMPONENT_ARCHIVE_HASH=	\
    sha256:e8f7dfb70c2039d7a868dcd4c150e88bc5628b5488d24a67287b1597206a7bdc
COMPONENT_ARCHIVE_URL=	http://download.transmissionbt.com/files/$(COMPONENT_ARCHIVE)
COMPONENT_LICENSE_FILE=	COPYING
COMPONENT_LICENSE=	GPLv2,MIT


include $(WS_TOP)/make-rules/prep.mk
include $(WS_TOP)/make-rules/configure.mk
include $(WS_TOP)/make-rules/ips.mk

PATH=/usr/gnu/bin:/usr/bin

CONFIGURE_OPTIONS+=	--program-prefix=""

# common targets
build:		$(BUILD_32)

install:	$(INSTALL_32)

test:		$(NO_TESTS)
