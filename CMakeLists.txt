cmake_minimum_required(VERSION 3.10.3)
project(imada)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")

add_custom_target(build-imada ALL
        COMMAND ./autogen.sh
        COMMAND ./configure
        COMMAND $(MAKE) WORKING_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}
        COMMAND $(MAKE))

add_custom_target(debug-imadad ALL)
add_custom_target(debug-imada-qt ALL)