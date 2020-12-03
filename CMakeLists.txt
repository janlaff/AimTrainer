cmake_minimum_required(VERSION 3.17)
project(AimTrainer)

set(CMAKE_CXX_STANDARD 20)

include(cmake/CPM.cmake)

add_subdirectory(app)
add_subdirectory(ecs)
add_subdirectory(gfx)