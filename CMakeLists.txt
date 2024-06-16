cmake_minimum_required(VERSION 3.9)
project(oscpp VERSION 0.3.0)

if (CMAKE_SYSTEM_NAME STREQUAL "Linux")
    set(LINUX TRUE)
endif ()

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_C_STANDARD 99)

include(GNUInstallDirs)

add_library(oscpp INTERFACE
    include/oscpp/client.hpp
    include/oscpp/error.hpp
    include/oscpp/print.hpp
    include/oscpp/server.hpp
    include/oscpp/types.hpp
    include/oscpp/util.hpp
    include/oscpp/detail/endian.hpp
    include/oscpp/detail/host.hpp
    include/oscpp/detail/stream.hpp
)

target_include_directories(oscpp INTERFACE ${CMAKE_CURRENT_SOURCE_DIR}/include)

enable_testing()

add_subdirectory(test)

