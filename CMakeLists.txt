project(flint C)

cmake_minimum_required(VERSION 3.4)

set(CMAKE_MODULE_PATH ${PROJECT_SOURCE_DIR}/cmake)

set(CMAKE_BUILD_TYPE Release)

option(BUILD_SHARED_LIBS "build shared libraries" ON)

set(CMAKE_WINDOWS_EXPORT_ALL_SYMBOLS ON)

find_package(GMP REQUIRED)
include_directories(SYSTEM ${GMP_INCLUDE_DIRS})
set(LIBS ${LIBS} ${GMP_TARGETS})

include_directories(BEFORE ${CMAKE_CURRENT_SOURCE_DIR})

set(FLINT_SOURCES
    ulong_extras/gcd.c
    ulong_extras/gcdinv.c
    ulong_extras/ll_mod_preinv.c
    ulong_extras/mod2_preinv.c
    ulong_extras/mulmod_preinv.c
    ulong_extras/powmod2_ui_preinv.c
    ulong_extras/dummy.c
    generic_files/clz_tab.c
    )

add_library(flint ${FLINT_SOURCES})

set(FLINT_HEADERS
    flint.h
    longlong.h
    nmod_vec.h
    ulong_extras.h
    )

install(FILES ${FLINT_HEADERS} DESTINATION include/flint)
install(TARGETS flint ARCHIVE DESTINATION lib LIBRARY DESTINATION lib RUNTIME DESTINATION bin)
