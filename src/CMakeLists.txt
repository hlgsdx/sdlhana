string(TIMESTAMP BUILDDATE "%Y-%m-%d")
string(TIMESTAMP BUILDTIME "%H:%M:%S")

add_compile_definitions(COMPILER=\"${CMAKE_CXX_COMPILER_ID}\")
add_compile_definitions(COMPILER_VERSION=\"${CMAKE_CXX_COMPILER_VERSION}\")
add_compile_definitions(CMAKE_VERSION=\"${CMAKE_VERSION}\")

file(GLOB sdlhana_SRC "*.h" "*.cpp")
include_directories(${SDL_INCLUDE_DIR})
add_executable(sdlhana ${sdlhana_SRC})
set_target_properties(
        sdlhana PROPERTIES
        RUNTIME_OUTPUT_DIRECTORY ${CMAKE_SOURCE_DIR}/app)
target_link_libraries(sdlhana ${SDL_LIBRARY})

file(COPY ${CMAKE_CURRENT_SOURCE_DIR}/data DESTINATION ${CMAKE_SOURCE_DIR}/app)
file(COPY ${CMAKE_CURRENT_SOURCE_DIR}/fonts DESTINATION ${CMAKE_SOURCE_DIR}/app)
file(COPY ${CMAKE_CURRENT_SOURCE_DIR}/images DESTINATION ${CMAKE_SOURCE_DIR}/app)
file(COPY ${CMAKE_CURRENT_SOURCE_DIR}/sound DESTINATION ${CMAKE_SOURCE_DIR}/app)
