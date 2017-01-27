cmake_minimum_required (VERSION 3.3)

project (asterisk-opus)

add_compile_options(-pthread -g3 -O3 -D_FORTIFY_SOURCE=2 -fPIC)

# Build supports setting of sysroot but breaks if it is not set, so default it to /
if (NOT "--sysroot" IN_LIST COMPILEROPTIONS)
add_compile_options(--sysroot /)
endif ()

include_directories (${PROJECT_SOURCE_DIR}/include)

set(CMAKE_SHARED_LIBRARY_PREFIX)
set(CMAKE_SHARED_LINKER_FLAGS "${CMAKE_SHARED_LINKER_FLAGS} -pthread -Wl,--warn-common")

set(AST_MOD_DIR "${CMAKE_INSTALL_LIBDIR}/asterisk/modules")

add_subdirectory(codecs)
add_subdirectory(formats)
add_subdirectory(res)


