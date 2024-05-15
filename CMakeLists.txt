cmake_minimum_required(VERSION 3.20)

project(bad-snake)

add_subdirectory(doctest)
add_subdirectory(gmock)

add_executable(snake main.cpp)

add_executable(snake-tests snake-tests.cpp)
target_link_libraries(snake-tests doctest gmock_main)

enable_testing()
add_test(NAME snake-tests COMMAND snake-tests --force-colors -d)