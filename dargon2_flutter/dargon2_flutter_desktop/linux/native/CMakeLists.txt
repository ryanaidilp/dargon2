# Copyright 2020 Tejas Mehta <tmthecoder@gmail.com>
# Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:
# The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.
# THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

cmake_minimum_required(VERSION 3.19)

# CMake Instructions for Argon2's build for Android's NDK

project(argon2 C CXX)
set(CMAKE_CXX_FLAGS_RELEASE "${CMAKE_CXX_FLAGS_RELEASE} -Os")

file(GLOB argon2_SOURCES
       ./argon2/src/blake2/blake2b.c
       ./argon2/src/argon2.c
        ./argon2/src/core.c
        ./argon2/src/encoding.c
        ./argon2/src/ref.c
        ./argon2/src/thread.c
)

add_library(argon2 SHARED ${argon2_SOURCES})
target_compile_options(argon2 PRIVATE)
target_include_directories(argon2 PUBLIC ./argon2/include/)
