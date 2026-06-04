file(GLOB_RECURSE SANDBOX_SOURCES
    CONFIGURE_DEPENDS
    *.cpp
)

find_package(glfw3 3.3 REQUIRED)

add_executable(sandbox
    ${SANDBOX_SOURCES}
)

target_link_libraries(sandbox
    PRIVATE
        graphics
        glfw
)

target_compile_definitions(sandbox
    PRIVATE
        SHADER_DIR="${CMAKE_SOURCE_DIR}/libs/graphics/include/"
        TEXTURE_DIR="${CMAKE_SOURCE_DIR}/libs/graphics/texture/"
)
