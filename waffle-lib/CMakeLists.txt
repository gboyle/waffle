
add_library(
    waffle-lib
    lib.cpp
)

target_include_directories(waffle-lib PUBLIC ${CMAKE_CURRENT_SOURCE_DIR} ${CMAKE_CURRENT_SOURCE_DIR}/tests)

target_link_libraries(waffle-lib fmt::fmt)
target_link_libraries(waffle-lib spdlog::spdlog)
