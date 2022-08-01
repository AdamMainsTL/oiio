# Copyright 2008-present Contributors to the OpenImageIO project.
# SPDX-License-Identifier: BSD-3-Clause
# https://github.com/OpenImageIO/oiio

if (TARGET OpenJPEG::OpenJPEG)
    add_oiio_plugin (jpeg2000input.cpp jpeg2000output.cpp
                     INCLUDE_DIRS ${OPENJPEG_INCLUDES}
                     LINK_LIBRARIES OpenJPEG::OpenJPEG
                     DEFINITIONS "-DUSE_OPENJPEG")
else()
    message (WARNING "Jpeg-2000 plugin will not be built")
endif()
