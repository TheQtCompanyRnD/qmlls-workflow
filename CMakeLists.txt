# Copyright (C) 2024 The Qt Company Ltd.
# SPDX-License-Identifier: BSD-3-Clause

cmake_minimum_required(VERSION 3.16)

project(qmlls VERSION 0.1 LANGUAGES CXX)

set(CMAKE_CXX_STANDARD_REQUIRED ON)

find_package(Qt6 REQUIRED COMPONENTS QmlLSPrivate QmlCompiler QmlToolingSettingsPrivate Help)

qt_standard_project_setup(REQUIRES 6.8)

qt_add_executable(qmlls WIN32 qmllanguageservertool.cpp)

target_link_libraries(qmlls
    PRIVATE
        Qt::QmlLSPrivate
        Qt::Help
)
