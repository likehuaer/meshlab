# Copyright 2019-2020, Collabora, Ltd.
# SPDX-License-Identifier: BSL-1.0


set(SOURCES filter_trioptimize.cpp)

set(HEADERS curvdata.h curvedgeflip.h filter_trioptimize.h)

add_library(filter_trioptimize MODULE ${SOURCES} ${HEADERS})

target_include_directories(filter_trioptimize
                           PRIVATE ${CMAKE_CURRENT_SOURCE_DIR})
target_link_libraries(filter_trioptimize PUBLIC meshlab-common)

set_property(TARGET filter_trioptimize PROPERTY FOLDER Plugins)

set_property(TARGET filter_trioptimize PROPERTY RUNTIME_OUTPUT_DIRECTORY
                                                ${MESHLAB_PLUGIN_OUTPUT_DIR})

set_property(TARGET filter_trioptimize PROPERTY LIBRARY_OUTPUT_DIRECTORY
                                                ${MESHLAB_PLUGIN_OUTPUT_DIR})

install(
    TARGETS filter_trioptimize
    DESTINATION ${MESHLAB_PLUGIN_INSTALL_DIR}
    COMPONENT Plugins)
