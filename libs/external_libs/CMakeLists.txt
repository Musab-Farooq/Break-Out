# GLAD

add_library(glad STATIC
    src/glad.c
)

target_include_directories(glad
    PUBLIC
        ${CMAKE_CURRENT_SOURCE_DIR}/include
)

# GLM

add_library(glm INTERFACE)

target_include_directories(glm
    INTERFACE
        ${CMAKE_CURRENT_SOURCE_DIR}/include/glm
)