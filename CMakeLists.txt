cmake_minimum_required(VERSION 3.1)
project(game.libretro.meteor)

list(APPEND CMAKE_MODULE_PATH ${PROJECT_SOURCE_DIR})

find_package(Kodi REQUIRED)
find_package(libretro-meteor REQUIRED)

set(METEOR_CUSTOM_BINARY ${METEOR_LIB}
    ${PROJECT_NAME}${CMAKE_SHARED_LIBRARY_SUFFIX})

build_addon(${PROJECT_NAME} METEOR "")