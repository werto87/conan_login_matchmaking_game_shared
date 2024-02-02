cmake_minimum_required(VERSION 3.12)
project(test_package LANGUAGES CXX)

find_package(login_matchmaking_game_shared REQUIRED CONFIG)

add_executable(${PROJECT_NAME} test_package.cpp)
target_link_libraries(${PROJECT_NAME} PRIVATE login_matchmaking_game_shared::login_matchmaking_game_shared)
target_compile_definitions(${PROJECT_NAME} PRIVATE
        PATH_TO_USER_DEFINED_GAME_OPTION="userDefinedGameOption.hxx"
        )
target_include_directories(${PROJECT_NAME} PRIVATE ${CMAKE_CURRENT_SOURCE_DIR} ${CMAKE_SOURCE_DIR})
