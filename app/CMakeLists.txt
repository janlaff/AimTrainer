cmake_minimum_required(VERSION 3.17)

file(GLOB_RECURSE SOURCE_FILES CONFIGURE_DEPENDS src/*.cpp)

add_executable(AimTrainer ${SOURCE_FILES})
target_link_libraries(AimTrainer ecs gfx)