cmake_minimum_required(VERSION 3.0)
#The following line is added in order to generate .lib file as well apart from dll for ShreyaDynamic
SET(CMAKE_WINDOWS_EXPORT_ALL_SYMBOLS ON)

#ALL FILES BURRIED TOGETHER
add_executable(MAIN_ALL_FILES_BURRIED shreya.cpp main.cpp shreya.h)

#STATIC LIBRARY
add_library(ShreyaStatic Shreya.h Shreya.cpp)
add_executable(MAIN_WITH_STATIC_LIB main.cpp)
target_link_libraries(MAIN_WITH_STATIC_LIB ShreyaStatic)

#DYNAMIC LIBRARY (DLL)
add_library(ShreyaDynamic SHARED  Shreya.h Shreya.cpp)
add_executable(MAIN_WITH_Dynamic_LIB main.cpp)
target_link_libraries(MAIN_WITH_Dynamic_LIB ShreyaDynamic)