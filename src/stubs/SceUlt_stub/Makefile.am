# Copyright (C) 2015 PSP2SDK Project
#
# This Source Code Form is subject to the terms of the Mozilla Public
# License, v. 2.0. If a copy of the MPL was not distributed with this
# file, You can obtain one at http://mozilla.org/MPL/2.0/.

PREFIX = _SceUlt-0001_
ENTRIES_PREFIX = $(PREFIX)F00_

NIDS = 0x001eac8a 0x04dc59f2 0x0603fcc1 0x10b3fb76 	\
	0x1470318d 0x14da1bb4 0x1ad58a53 0x1e401df8 	\
	0x218d4743 0x24d87e05 0x25fe84f3 0x2629c055 	\
	0x2a1a8ea6 0x2a5741f5 0x2b8d33f1 0x2cd0f57c 	\
	0x2fb0eb32 0x40856827 0x4e9a745c 0x4f6a7da6 	\
	0x53420ed2 0x5435c586 0x58d8dde6 0x5afec7a1 	\
	0x62f9493e 0x63483381 0x644da029 0x65376e2d 	\
	0x6d356b29 0x750e7962 0x7f373376 0x8486dde6 	\
	0x86dda3ae 0x897c9097 0x8a4f88a2 0x8e31b9fe 	\
	0x8ec57420 0x944fb222 0x9ad07630 0x9fe7cb9f 	\
	0xa798c5d7 0xa7e78ff9 0xaf15606d 0xb1290375 	\
	0xb1feb79b 0xb4cf88ac 0xb5895640 0xc7aa4779 	\
	0xc9e96714 0xcad57bad 0xd76a156c 0xd8334a1f 	\
	0xdd59562c 0xe5936a69 0xebb6fc1e 0xecda7fee 	\
	0xeebd9052 0xef094e35 0xf220d3ae 0xf37862de 	\
	0xf5f63e2c 0xf7a83023

ENTRIES = $(addsuffix .o,$(addprefix $(ENTRIES_PREFIX),$(subst 0x,,$(NIDS))))

lib_LIBRARIES = libSceUlt_stub.a
libSceUlt_stub_a_SOURCES = SceUlt_stub.S
am_libSceUlt_stub_a_OBJECTS =	\
	$(PREFIX)head.o $(PREFIX)NIDS.o $(ENTRIES)

$(PREFIX)head.o: $(libSceUlt_stub_a_SOURCES)
	$(COMPILE) -DHEAD $< -c -o $@

$(PREFIX)NIDS.o: $(libSceUlt_stub_a_SOURCES)
	$(COMPILE) -DNIDS $< -c -o $@

$(ENTRIES): $(libSceUlt_stub_a_SOURCES)
	$(COMPILE) -DFUNC=$(subst $(ENTRIES_PREFIX),0x,$*) $< -c -o $@
