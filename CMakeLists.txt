cmake_minimum_required(VERSION 3.28.0)

project(aladin_practise_cur1 VERSION 0.1.0 LANGUAGES C CXX)

set(CMAKE_CXX_STANDARD 17)

set(PKG_CONFIG_EXECUTABLE "C:\\msys64\\mingw64\\bin\\pkg-config")

set(GTK3_INCLUDE_DIRS "C:\\msys64\\mingw64\\include")
set(GTK3_LIBRARY_DIRS "C:\\msys64\\mingw64\\lib") 
set(ENV{PKG_CONFIG_PATH} "C:\\msys64\\mingw64\\lib\\pkgconf")

find_package(PkgConfig REQUIRED)
pkg_check_modules(GTK4 REQUIRED IMPORTED_TARGET gtk4)
 
include_directories(${GTK4_INCLUDE_DIRS})
link_directories(${GTK4_LIBRARY_DIRS})
add_definitions(${GTK4_CFLAGS_OTHER})

# set_target_properties(aladin_practise_cur1 PROPERTIES WIN32_EXECUTABLE true)
# target_link_libraries(aladin_practise_cur1 ${GTK4_LIBRARIES})

add_executable(aladin_practise_cur1 exmaple-0.c)
target_link_libraries(aladin_practise_cur1 PRIVATE PkgConfig::GTK4)
 