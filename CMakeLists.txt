cmake_minimum_required(VERSION 3.1)
project(sample CXX)

find_package(PkgConfig REQUIRED) 
pkg_check_modules(GLFW3 REQUIRED glfw3)
pkg_check_modules(GL REQUIRED gl)

set(CMAKE_CXX_FLAGS "${GLFW3_CFLAGS} ${GL_CFLAGS}")

add_executable(${PROJECT_NAME} main.cpp)
target_link_libraries(${PROJECT_NAME} ${GLFW3_LIBRARIES})
target_link_libraries(${PROJECT_NAME} ${GL_LIBRARIES})
