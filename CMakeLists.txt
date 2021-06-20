cmake_minimum_required(VERSION 3.19)
project(SFMLtcpsockettutorial)

set(EXECUTABLE_NAME "SFMLtcpsockettutorial")

set(CMAKE_CXX_STANDARD 14)

add_executable(SFMLtcpsockettutorial main.cpp)


# Detect and add SFML
set(CMAKE_MODULE_PATH "${CMAKE_SOURCE_DIR}/cmake_modules" ${CMAKE_MODULE_PATH})
#Find any version 2.X of SFML
#See the FindSFML.cmake file for additional details and instructions
find_package(SFML 2 REQUIRED network audio graphics window system)
if(SFML_FOUND)
    include_directories(${SFML_INCLUDE_DIR})
    target_link_libraries(${EXECUTABLE_NAME} ${SFML_LIBRARIES} ${SFML_DEPENDENCIES})
endif()
