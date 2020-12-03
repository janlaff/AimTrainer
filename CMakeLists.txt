cmake_minimum_required(VERSION 3.17)
project(AimTrainer)

set(CMAKE_CXX_STANDARD 20)

include(cmake/CPM.cmake)

CPMAddPackage(
        NAME libglew_static
        GITHUB_REPOSITORY Perlmint/glew-cmake
        GIT_TAG glew-cmake-2.1.0
)

CPMAddPackage(
        NAME glm
        GITHUB_REPOSITORY g-truc/glm
        GIT_TAG 0.9.9.8
)

CPMAddPackage(
        NAME glfw
        GITHUB_REPOSITORY glfw/glfw
        GIT_TAG 3.3.2
)

CPMAddPackage(
        NAME EnTT
        GITHUB_REPOSITORY skypjack/entt
        VERSION 3.5.2
)

file(GLOB_RECURSE SOURCE_FILES CONFIGURE_DEPENDS src/*.cpp)

add_executable(AimTrainer ${SOURCE_FILES})
target_link_libraries(AimTrainer libglew_static glm glfw EnTT)