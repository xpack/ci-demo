#
# This file is part of the xPack project (http://xpack.github.io).
# Copyright (c) 2023 Liviu Ionescu. All rights reserved.
#
# This Software is provided under the terms of the MIT License.
# If a copy of the license was not distributed with this file, it can
# be obtained from https://opensource.org/licenses/MIT/.
#
# -----------------------------------------------------------------------------

cmake_minimum_required(VERSION 3.20)

project(
  hello
  DESCRIPTION "A simple Hello World application"
)

enable_language(C)
enable_language(CXX)

set(CMAKE_C_STANDARD 11)
set(CMAKE_C_STANDARD_REQUIRED ON)
set(CMAKE_C_EXTENSIONS OFF)

set(CMAKE_CXX_STANDARD 20) # 11, 13, 17, 20
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

if(CMAKE_BINARY_DIR STREQUAL CMAKE_SOURCE_DIR)
  message(FATAL_ERROR "In-source builds are not supported. Please use separate folder for build.")
endif()

enable_testing()

# -----------------------------------------------------------------------------

add_executable(hello)

target_sources(
    hello

    PRIVATE
      src/main.cpp
)

# -----------------------------------------------------------------------------

add_test(
  NAME "hello"
  COMMAND hello
)

# -----------------------------------------------------------------------------
