cmake_minimum_required(VERSION 3.1)
project(net_mul)

set(CMAKE_CXX_STANDARD 14)

set(CMAKE_CXX_FLAGS_DEBUG "${CMAKE_CXX_FLAGS_DEBUG} -D_GLIBCXX_DEBUG -fsanitize=address,undefined")
set(CMAKE_CXX_FLAGS_RELEASE "-O2")

add_library(utils STATIC utils.cpp fd_wrapper.h)

add_executable(server server.cpp)
add_executable(client client.cpp)

TARGET_LINK_LIBRARIES(server utils)
TARGET_LINK_LIBRARIES(client utils)
