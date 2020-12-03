cmake_minimum_required(VERSION 3.17)

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

file(GLOB_RECURSE SOURCE_FILES CONFIGURE_DEPENDS src/*.cpp src/*.hpp include/*.hpp)

add_library(gfx STATIC ${SOURCE_FILES})
target_include_directories(gfx PUBLIC include PRIVATE src)
target_link_libraries(gfx libglew_static glm glfw)