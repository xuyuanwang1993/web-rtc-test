cmake_minimum_required(VERSION 3.16)
get_filename_component(current_project_name ${CMAKE_CURRENT_LIST_DIR} NAME)
set(project_name ${current_project_name})
project(${project_name} VERSION 0.1 LANGUAGES CXX)

set(CURRENT_PROJECT_ROOT ${CMAKE_CURRENT_SOURCE_DIR})
if(MSVC)
    set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} /std:c++17 /Zc:__cplusplus")
endif()

add_subdirectory(openssl-static/win)
find_package(OpenSSL REQUIRED)
add_subdirectory(libdatachannel)
add_subdirectory(src)





