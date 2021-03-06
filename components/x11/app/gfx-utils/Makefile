#
# CDDL HEADER START
#
# The contents of this file are subject to the terms of the
# Common Development and Distribution License (the "License").
# You may not use this file except in compliance with the License.
#
# You can obtain a copy of the license at usr/src/OPENSOLARIS.LICENSE
# or http://www.opensolaris.org/os/licensing.
# See the License for the specific language governing permissions
# and limitations under the License.
#
# When distributing Covered Code, include this CDDL HEADER in each
# file and include the License file at usr/src/OPENSOLARIS.LICENSE.
# If applicable, add the following below this CDDL HEADER, with the
# fields enclosed by brackets "[]" replaced with your own identifying
# information: Portions Copyright [yyyy] [name of copyright owner]
#
# CDDL HEADER END
#

#
# Copyright (c) 2019, Oracle and/or its affiliates. All rights reserved.
#

BUILD_BITS= 		64
BUILD_ARCH=		sparc

# Parallel build jobs are supported only if GNU make is used.
COMPONENT_MAKE_JOBS=1

include ../../../../make-rules/shared-macros.mk

COMPONENT_NAME=         gfx-utils
COMPONENT_VERSION=      #
COMPONENT_SRC=          sun-src
COMPONENT_ARCHIVE=	
COMPONENT_ARCHIVE_SRC=	none
COMPONENT_BUGDB=	x11/xclients
COMPONENT_ANITYA_ID=	N/A

# nothing to download ; just build & package
BUILD_STYLE= justmake
TEST_TARGET= $(NO_TESTS)

DMAKE = $(SPRO_VROOT)/bin/dmake
LDFLAGS += $(CC_BITS)
COMPONENT_BUILD_ENV += LIB_LDFLAGS="$(LDFLAGS)"
COMPONENT_INSTALL_ENV += INSTALL="$(INSTALL) -D"

COMPONENT_BUILD_ACTION = \
        cd $(@D); $(ENV) $(COMPONENT_BUILD_ENV) \
        $(DMAKE) $(COMPONENT_BUILD_ARGS) $(COMPONENT_BUILD_TARGETS)

COMPONENT_INSTALL_ACTION = \
        cd $(@D) ; $(ENV) $(COMPONENT_INSTALL_ENV) \
        $(DMAKE) $(COMPONENT_INSTALL_ARGS) $(COMPONENT_INSTALL_TARGETS)

include $(WS_MAKE_RULES)/x11-component.mk

REQUIRED_PACKAGES += system/library/math
REQUIRED_PACKAGES += system/library/smf
REQUIRED_PACKAGES += x11/library/libx11
REQUIRED_PACKAGES += x11/library/libxext
