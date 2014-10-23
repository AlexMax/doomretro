cmake_minimum_required(VERSION 2.8)

project("Doom Retro" C)

set(CMAKE_MODULE_PATH "${CMAKE_SOURCE_DIR}/cmake")

find_package(SDL2 COMPONENTS mixer)

if(NOT ${SDL_FOUND})
  message(FATAL_ERROR "SDL not found")
elseif(NOT ${SDLMIXER_FOUND})
  message(FATAL_ERROR "SDL_mixer not found")
endif()

include_directories(${SDL_INCLUDE_DIR} ${SDLMIXER_INCLUDE_DIR})

file(GLOB DOOM_HEADERS "src/*.h")
file(GLOB DOOM_SOURCES "src/*.c")

add_executable(doomretro ${DOOM_SOURCES})
target_link_libraries(doomretro ${SDL_LIBRARY} ${SDLMIXER_LIBRARY})
