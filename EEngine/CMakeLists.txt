cmake_minimum_required (VERSION 3.2)
project (EEngine)
SET(PROJECT_NAME EEngine)

# set(CMAKE_DEBUG_POSTFIX "_d")
# set(CMAKE_RELEASE_POSTFIX "_r")

set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY_DEBUG ${PROJECT_SOURCE_DIR}/../lib)
set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY_RELEASE ${PROJECT_SOURCE_DIR}/../lib)

# lib dir
SET(PROJECT_LIB_DIR ${PROJECT_SOURCE_DIR}/../lib)

# libs name
SET(PROJECT_LIBS ${PROJECT_LIB_DIR}/ECore.lib)

include_directories(${PROJECT_SOURCE_DIR}/include
${PROJECT_SOURCE_DIR}/../ECore/include)

# source
aux_source_directory(${PROJECT_SOURCE_DIR}/src SRC_LIST)

# generator lib SHARED
add_library(${PROJECT_NAME} STATIC ${SRC_LIST})

target_link_libraries(${PROJECT_NAME} ${PROJECT_LIBS})