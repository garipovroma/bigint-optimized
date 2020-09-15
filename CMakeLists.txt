cmake_minimum_required(VERSION 2.8)

project(BIGINT)
set(CMAKE_CXX_STANDARD 11)

include_directories(${BIGINT_SOURCE_DIR})

add_executable(big_integer_testing
        tests/big_integer_testing.cpp
        big_integer/big_integer.h
        big_integer/big_integer.cpp
               gtest/gtest-all.cc
               gtest/gtest.h
               gtest/gtest_main.cc
        tests/big_integer_gmp.cpp
        tests/big_integer_gmp.h big_integer/storage.h big_integer/buffer.h big_integer/storage.cpp big_integer/buffer.cpp)

if(CMAKE_COMPILER_IS_GNUCC OR CMAKE_COMPILER_IS_GNUCXX)
  set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wall -pedantic")
  set(CMAKE_CXX_FLAGS_DEBUG "${CMAKE_CXX_FLAGS_DEBUG} -fsanitize=undefined,address,leak -fno-sanitize-recover=all -D_GLIBCXX_DEBUG")
endif()

target_link_libraries(big_integer_testing -lgmp -lpthread)
