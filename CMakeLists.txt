cmake_minimum_required(VERSION 3.14)

project(glsw)

add_library(glsw STATIC 
	"src/bstrlib.c"
	"src/bstrlib.h"
	"src/glsw.c"
)

target_include_directories(glsw PUBLIC "${CMAKE_CURRENT_SOURCE_DIR}/include")
