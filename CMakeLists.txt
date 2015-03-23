project(game.libretro.meteor)

cmake_minimum_required(VERSION 2.6)

list(APPEND CMAKE_MODULE_PATH ${PROJECT_SOURCE_DIR})

enable_language(CXX)

find_package(kodi REQUIRED)

include(ExternalProject)
externalproject_add(meteor
                    GIT_REPOSITORY https://github.com/libretro/meteor-libretro
                    GIT_TAG e877cf0
                    PREFIX meteor
                    CONFIGURE_COMMAND ""
                    INSTALL_COMMAND ""
                    BUILD_COMMAND make -C libretro
                    BUILD_IN_SOURCE 1)

set(METEOR_CUSTOM_BINARY ${PROJECT_BINARY_DIR}/meteor/src/meteor/libretro/meteor_libretro${CMAKE_SHARED_LIBRARY_SUFFIX}
                         game.libretro.meteor${CMAKE_SHARED_LIBRARY_SUFFIX} meteor)

build_addon(game.libretro.meteor METEOR DEPLIBS)
add_dependencies(game.libretro.meteor meteor)

include(CPack)
