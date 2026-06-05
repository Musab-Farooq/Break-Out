# GLAD

add_library(glad STATIC
    src/glad.c
)

target_include_directories(glad
    PUBLIC
        ${CMAKE_CURRENT_SOURCE_DIR}/include
)

# stb_image

add_library(stb_image STATIC
    src/stb_image_impl.cpp
)

target_include_directories(stb_image PUBLIC
    ${CMAKE_CURRENT_SOURCE_DIR}/include
)

# GLM

add_library(glm INTERFACE)

target_include_directories(glm
    INTERFACE
        ${CMAKE_CURRENT_SOURCE_DIR}/include/glm
)

# GLFW (Build from source instead of defining an interface)
set(GLFW_BUILD_DOCS OFF CACHE INTERNAL "")
set(GLFW_BUILD_TESTS OFF CACHE INTERNAL "")
set(GLFW_BUILD_EXAMPLES OFF CACHE INTERNAL "")

add_subdirectory(include/glfw)