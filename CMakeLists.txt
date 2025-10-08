# Copyright (C) 2024 The Qt Company Ltd.
# SPDX-License-Identifier: BSD-3-Clause

cmake_minimum_required(VERSION 3.16)

project(qmlls VERSION 0.5 LANGUAGES CXX)

set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(QT_NO_EXCEPTIONS ON)

find_package(Qt6 REQUIRED COMPONENTS QmlLSPrivate Help)

qt_standard_project_setup(REQUIRES 6.8)

qt_add_executable(qmlls WIN32 qmllanguageservertool.cpp)

# keep binary size of qmlls small, exclude plugins that are not needed
qt_import_plugins(qmlls
    EXCLUDE_BY_TYPE
        imageformats
        iconengines
        qmltooling
        styles
        networkaccess
        networkinformation
        tls
        qmlmeta
        qmlworkerscript
        qmlmodels
        quick
        qml_plugin
        platforms)

target_link_libraries(qmlls
    PRIVATE
        Qt::QmlLSPrivate
        Qt::Help
)
