project(game.libretro.meteor)

cmake_minimum_required(VERSION 2.6)

list(APPEND CMAKE_MODULE_PATH ${PROJECT_SOURCE_DIR})

enable_language(CXX)

find_package(kodi REQUIRED)
find_package(libretro-meteor REQUIRED)

set(DEPLIBS meteor)
set(METEOR_CUSTOM_BINARY ${METEOR_LIB}
                         game.libretro.meteor${CMAKE_SHARED_LIBRARY_SUFFIX} meteor)

build_addon(game.libretro.meteor METEOR DEPLIBS)
