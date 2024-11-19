cmake_minimum_required(VERSION 3.12)

project(CG_ProjTerreno)

# Add the main executable
add_executable(CG_ProjTerreno main.cpp "main.cpp")

# Include directories for dependencies
target_include_directories(CG_ProjTerreno PRIVATE 
    deps/glm 
    deps/glfw/include
    deps/glew/include
    deps/assimp/include  # Add Assimp include directory
)

# Link directories for dependencies
target_link_directories(CG_ProjTerreno PRIVATE 
    deps/glfw/lib-vc2019
    deps/glew/lib/Release/x64
    deps/assimp/lib  # Add Assimp library directory
)

# Link libraries
target_link_libraries(CG_ProjTerreno PRIVATE 
    glfw3.lib 
    glew32.lib 
    opengl32.lib 
    assimp-vc143-mt.lib  # Replace with the actual Assimp library name you are using
)

# Add post-build commands to copy required DLLs
add_custom_command(TARGET CG_ProjTerreno POST_BUILD
    COMMAND ${CMAKE_COMMAND} -E copy "${CMAKE_SOURCE_DIR}/deps/glew/bin/Release/x64/glew32.dll" "${CMAKE_BINARY_DIR}/glew32.dll"
    COMMAND ${CMAKE_COMMAND} -E copy "${CMAKE_SOURCE_DIR}/deps/assimp/bin/assimp-vc143-mt.dll" "${CMAKE_BINARY_DIR}/assimp-vc143-mt.dll"  # Replace with the actual Assimp DLL
    COMMAND ${CMAKE_COMMAND} -E copy "${CMAKE_SOURCE_DIR}/deps/assimp/bin/poly2tri.dll" "${CMAKE_BINARY_DIR}/poly2tri.dll"
    COMMAND ${CMAKE_COMMAND} -E copy "${CMAKE_SOURCE_DIR}/deps/assimp/bin/minizip.dll" "${CMAKE_BINARY_DIR}/minizip.dll"
    COMMAND ${CMAKE_COMMAND} -E copy "${CMAKE_SOURCE_DIR}/deps/assimp/bin/zlib1.dll" "${CMAKE_BINARY_DIR}/zlib1.dll"
    COMMAND ${CMAKE_COMMAND} -E copy "${CMAKE_SOURCE_DIR}/deps/assimp/bin/pugixml.dll" "${CMAKE_BINARY_DIR}/pugixml.dll"
)