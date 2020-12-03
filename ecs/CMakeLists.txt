cmake_minimum_required(VERSION 3.17)

file(GLOB_RECURSE SOURCE_FILES CONFIGURE_DEPENDS src/*.cpp src/*.hpp include/*.hpp)

add_library(ecs STATIC ${SOURCE_FILES})
target_include_directories(ecs PUBLIC include PRIVATE src)
