# Copyright 2008-present Contributors to the OpenImageIO project.
# SPDX-License-Identifier: BSD-3-Clause
# https://github.com/OpenImageIO/oiio

if (TARGET libraw::libraw)
    add_oiio_plugin (rawinput.cpp rawoutput.cpp
		INCLUDE_DIRS ${LibRaw_INCLUDE_DIR} ${TIFF_INCLUDE_DIR}
		LINK_LIBRARIES libraw::libraw ${TIFF_LIBRARIES} ZLIB::ZLIB
                     DEFINITIONS "-DUSE_LIBRAW=1" ${LibRaw_r_DEFINITIONS})
else ()
    add_oiio_plugin (rawoutput.cpp
                     INCLUDE_DIRS ${TIFF_INCLUDE_DIR}
					 LINK_LIBRARIES ${TIFF_LIBRARIES} ZLIB::ZLIB)
endif ()
