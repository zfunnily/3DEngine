cmake_minimum_required (VERSION 3.2)
project (ECore)
SET(PROJECT_NAME ECore)

# set(CMAKE_DEBUG_POSTFIX "_d")
# set(CMAKE_RELEASE_POSTFIX "_r")

set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY_DEBUG ${PROJECT_SOURCE_DIR}/../lib)
set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY_RELEASE ${PROJECT_SOURCE_DIR}/../lib)

file(GLOB_RECURSE pipe_header_files  ${CMAKE_CURRENT_SOURCE_DIR}/include/*.h )
source_group("Header Files" FILES ${pipe_header_files}) 


include_directories(${PROJECT_SOURCE_DIR}/include)
aux_source_directory(${PROJECT_SOURCE_DIR}/src SRC_LIST)

add_library(${PROJECT_NAME} STATIC ${SRC_LIST} ${pipe_header_files})