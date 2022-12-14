cmake_minimum_required(VERSION 3.0.0)
project(cpp_covid_game VERSION 0.1.0)

include(CTest)
enable_testing()

add_executable(cpp_covid_game src/main.cpp)
add_library(vector2 src/vector2/vector2.cpp)
add_library(utilities src/utilities/utilities.cpp)
add_library(player src/player/player.cpp)
add_library(entity src/entity/entity.cpp)
target_link_libraries(cpp_covid_game vector2 utilities player entity)

set(CPACK_PROJECT_NAME ${PROJECT_NAME})
set(CPACK_PROJECT_VERSION ${PROJECT_VERSION})

if(MSVC)
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} /std:c++17")
endif(MSVC)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

include(CPack)
