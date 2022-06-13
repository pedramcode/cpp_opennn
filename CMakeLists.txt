cmake_minimum_required(VERSION "3.22.1")

project("project")

set(SRC_DIR "${CMAKE_CURRENT_LIST_DIR}/src")
set(INCLUDE_DIR "${CMAKE_CURRENT_LIST_DIR}/include")
add_executable(${PROJECT_NAME})

find_library(opennn REQUIRED)


file(GLOB PROJECT_SOURCE_FILES "${SRC_DIR}/*.cc")
target_sources(${PROJECT_NAME}
    PRIVATE
    ${PROJECT_SOURCE_FILES}
)

target_include_directories(${PROJECT_NAME}
    PRIVATE
    ${INCLUDE_DIR}
)