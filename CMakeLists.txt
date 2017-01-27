cmake_minimum_required (VERSION 2.6)

project (asterisk-opus)

find_library(asterisk REQUIRED)
find_library(OPUS opus REQUIRED)
find_library(opusfile REQUIRED)


add_compile_options(-pthread -g3 -O3 -D_FORTIFY_SOURCE=2 -fPIC)

include_directories (${PROJECT_SOURCE_DIR}/include)

set(CMAKE_SHARED_LIBRARY_PREFIX)
set(CMAKE_SHARED_LINKER_FLAGS "${CMAKE_SHARED_LINKER_FLAGS} -pthread -Wl,--warn-common")

set(AST_MOD_DIR "${CMAKE_INSTALL_LIBDIR}/asterisk/modules")

add_subdirectory(codecs)
add_subdirectory(formats)
add_subdirectory(res)


