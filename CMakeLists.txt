cmake_minimum_required(VERSION 3.11)
cmake_policy(VERSION 3.11)

include("cmake/HunterGate.cmake")

HunterGate(
    URL "https://github.com/ruslo/hunter/archive/v0.23.27.tar.gz"
    SHA1 "70d75a25f895df3da00d8382417e8c2a08c93173"
)

project(waffle VERSION 0.0.1)

set(CMAKE_CXX_STANDARD 17)


hunter_add_package(fmt)
find_package(fmt CONFIG REQUIRED)

hunter_add_package(spdlog)
find_package(spdlog CONFIG REQUIRED)


add_subdirectory(waffle-lib)
add_subdirectory(waffle-test)
add_subdirectory(waffle-main)

set_property(DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR} PROPERTY VS_STARTUP_PROJECT waffle-main)

enable_testing()
add_test(NAME testwaffle COMMAND waffle-test)