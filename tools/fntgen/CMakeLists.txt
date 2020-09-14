include_directories(${SDL_TTF_INCLUDE_DIR})
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/../../src)
add_executable (fntgen fntgen.cpp ${CMAKE_CURRENT_SOURCE_DIR}/../../src/compress.cpp)
target_link_libraries(fntgen ${SDL_LIBRARY} ${SDL_TTF_LIBRARY})
