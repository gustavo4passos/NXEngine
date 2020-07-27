cmake_minimum_required(VERSION 3.0.0)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY bin)
project(NX_Engine)

include_directories(/usr/include)
include_directories(/usr/include/SDL)
include_directories(/usr/local/include)
include_directories(/usr/local/include/SDL)
include_directories(./)

configure_file(tilekey.dat bin/tilekey.dat COPYONLY)
configure_file(sprites.sif bin/sprites.sif COPYONLY)
configure_file(font.ttf bin/font.ttf COPYONLY)


file(GLOB ROOT_SOURCES ./*.cpp)
file(GLOB AI_SOURCES ./ai/*.cpp)
file(GLOB AUTOGEN ./autogen/*.cpp)
file(GLOB COMMON_SOURCES ./common/*.cpp)
file(GLOB ENDGAME_SOURCES ./endgame/*.cpp)
file(GLOB EXTRACT_SOURCES ./extract/*.cpp)
file(GLOB GRAPHICS_SOURCES ./graphics/*.cpp)
file(GLOB INTRO_SOURCES ./intro/*.cpp)
file(GLOB PAUSE_SOURCES ./pause/*.cpp)
file(GLOB siflib_SOURCES ./siflib/*.cpp)
file(GLOB SOUND_SOURCES ./sound/*.cpp)
file(GLOB TEXT_BOX_SOURCES ./TextBox/*.cpp)
file(GLOB AIBOSS_SOURCES ./ai/boss/*.cpp)
file(GLOB AI_EGG_SOURCES ./ai/egg/*.cpp)
file(GLOB AI_FINAL_BATTLE_SOURCES ./ai/final_battle/*.cpp)
file(GLOB AI_HELL_SOURCES ./ai/hell/*.cpp)
file(GLOB AI_LAST_CAVE_SOURCES ./ai/last_cave/*.cpp)
file(GLOB AI_MAZE_SOURCES ./ai/maze/*.cpp)
file(GLOB AI_NPC_SOURCES ./ai/npc/*.cpp)
file(GLOB AI_OSIDE_SOURCES ./ai/oside/*.cpp)
file(GLOB AI_PLANTATION_SOURCES ./ai/plantation/*.cpp)
file(GLOB AI_SAND_SOURCES ./ai/sand/*.cpp)
file(GLOB AI_SYM_SOURCES ./ai/sym/*.cpp)
file(GLOB AI_VILLAGE_SOURCES ./ai/village/*.cpp)
file(GLOB AI_WEAPONS_SOURCES ./ai/weapons/*.cpp)
file(GLOB AI_WEED_SOURCES ./ai/weed/*.cpp)
file(GLOB PLATFORM_SOURCES ./platform/Linux/*.c)

add_executable(NX_Engine
${ROOT_SOURCES}
${AI_SOURCES}
${COMMON_SOURCES}
${ENDGAME_SOURCES}
${AUTOGEN}
${EXTRACT_SOURCES}
${GRAPHICS_SOURCES}
${INTRO_SOURCES}
${PAUSE_SOURCES}
${siflib_SOURCES}
${SOUND_SOURCES}
${TEXT_BOX_SOURCES}
${AIBOSS_SOURCES}
${AI_EGG_SOURCES}
${AI_FINAL_BATTLE_SOURCES}
${AI_HELL_SOURCES}
${AI_LAST_CAVE_SOURCES}
${AI_MAZE_SOURCES}
${AI_NPC_SOURCES}
${AI_OSIDE_SOURCES}
${AI_PLANTATION_SOURCES}
${AI_SAND_SOURCES}
${AI_SYM_SOURCES}
${AI_VILLAGE_SOURCES}
${AI_WEAPONS_SOURCES}
${AI_WEED_SOURCES}
${PLATFORM_SOURCES})

target_link_libraries(NX_Engine -lSDLmain -lSDL -lSDL_ttf)