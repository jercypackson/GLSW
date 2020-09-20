cmake_minimum_required(VERSION 3.14)

project(glsw C)

#if(MSVC)
#    set(CMAKE_DEBUG_POSTFIX "d")
#    target_include_directories(glsw ${CMAKE_CURRENT_SOURCE_DIR})
#endif()

#target_include_directories(glsw ${CMAKE_CURRENT_BINARY_DIR} ${CMAKE_SOURCE_DIR})

add_library(glsw STATIC 
	"${CMAKE_CURRENT_SOURCE_DIR}/src/bstrlib.c"
	"${CMAKE_CURRENT_SOURCE_DIR}/src/bstrlib.h"
	"${CMAKE_CURRENT_SOURCE_DIR}/src/glsw.c"
	"${CMAKE_CURRENT_SOURCE_DIR}/include/glsw.h"
)

target_include_directories(glsw PUBLIC "${CMAKE_CURRENT_SOURCE_DIR}/include")

install(TARGETS glsw
    ARCHIVE DESTINATION "${CMAKE_INSTALL_PREFIX}/lib"
    LIBRARY DESTINATION "${CMAKE_INSTALL_PREFIX}/lib" )

install(FILES "${CMAKE_CURRENT_SOURCE_DIR}/include/glsw.h" DESTINATION "${CMAKE_INSTALL_PREFIX}/include")
