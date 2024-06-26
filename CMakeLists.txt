cmake_minimum_required(VERSION 3.25)
project(demo)

set(CMAKE_C_STANDARD 99)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

# set execuable output path
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}/bin)
# set library output path
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}/lib)
# set library path
set(CMAKE_LIBRARY_PATH ${CMAKE_CURRENT_SOURCE_DIR}/lib)
# set(CMAKE_BUILD_TYPE Debug)
set(CMAKE_BUILD_TYPE Release)
# Control whether to call the output directory function echo_dir
set(ECHO_DIR OFF)
# use this in sub directory
set(ALL_LIBS "")
set(ALL_INCS "")

function(echo_dir)
    message("INFO === Current path: ${CMAKE_CURRENT_SOURCE_DIR} === INFO")
    message("                         project binary dir: ${PROJECT_BINARY_DIR}")
    message("                         project source dir: ${PROJECT_SOURCE_DIR}")
    message("                 CMAKE CMAKE_BINARY_DIR dir: ${CMAKE_BINARY_DIR}")
    message("                 CMAKE CMAKE_SOURCE_DIR dir: ${CMAKE_SOURCE_DIR}")
    message("              CMAKE CMAKE_CACHEFILE_DIR dir: ${CMAKE_CACHEFILE_DIR}")
    message("           CMAKE CMAKE_INSTALL_NAME_DIR dir: ${CMAKE_INSTALL_NAME_DIR}")
    message("           CMAKE CMAKE_CURRENT_LIST_DIR dir: ${CMAKE_CURRENT_LIST_DIR}")
    message("         CMAKE CMAKE_CURRENT_BINARY_DIR dir: ${CMAKE_CURRENT_BINARY_DIR}")
    message("         CMAKE CMAKE_CURRENT_SOURCE_DIR dir: ${CMAKE_CURRENT_SOURCE_DIR}")
    message("        CMAKE CMAKE_INCLUDE_CURRENT_DIR dir: ${CMAKE_INCLUDE_CURRENT_DIR}")
    message("  CMAKE CMAKE_CURRENT_FUNCTION_LIST_DIR dir: ${CMAKE_CURRENT_FUNCTION_LIST_DIR}")
    message(" CMAKE CMAKE_FIND_PACKAGE_REDIRECTS_DIR dir: ${CMAKE_FIND_PACKAGE_REDIRECTS_DIR}")
    message("CMAKE CMAKE_BUILD_WITH_INSTALL_NAME_DIR dir: ${CMAKE_BUILD_WITH_INSTALL_NAME_DIR}")
endfunction(echo_dir)

if(ECHO_DIR)
    echo_dir()
endif(ECHO_DIR)

message("========== INFO 'inc' INFO ==========")
add_subdirectory(inc)
# message("所有头文件名称：${ALL_INCS}")
# message("INFO: subdirectory 'inc' compeleted.\n")
message("========== INFO 'inc' INFO ==========\n")

message("========== INFO 'lib' INFO ==========")
add_subdirectory(lib)
# message("所有库文件名称：${ALL_LIBS}")
# message("INFO: subdirectory 'lib' compeleted.\n")
message("========== INFO 'lib' INFO ==========\n")

message("========== INFO 'src' INFO ==========")
add_subdirectory(src)
message("WARN: 可执行文件名称：${PROJECT_NAME}")
message("WARN: 可执行文件路径：./bin")
# message("INFO: subdirectory 'src' compeleted.\n")
message("========== INFO 'src' INFO ==========\n")
