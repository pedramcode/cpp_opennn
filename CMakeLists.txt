cmake_minimum_required(VERSION "3.22.1")

project("project")

set(SRC_DIR "${CMAKE_CURRENT_LIST_DIR}/src")
set(INCLUDE_DIR "${CMAKE_CURRENT_LIST_DIR}/include")
set(LIB_DIR "${CMAKE_CURRENT_LIST_DIR}/lib")
add_executable(${PROJECT_NAME})

file(GLOB_RECURSE PROJECT_SOURCE_FILES "${SRC_DIR}/*.cc" "${LIB_DIR}/opennn/*.cc" "${LIB_DIR}/eigen/src/*.cc")
target_sources(${PROJECT_NAME}
    PRIVATE
    ${PROJECT_SOURCE_FILES}
)

target_include_directories(${PROJECT_NAME}
    PRIVATE
    ${INCLUDE_DIR}
    ${LIB_DIR}/opennn
    ${LIB_DIR}/eigen
)
