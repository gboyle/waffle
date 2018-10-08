
add_executable(
    waffle-test
    test.cpp
)

target_link_libraries(waffle-test waffle-lib)

set_target_properties(waffle-test PROPERTIES VS_DEBUGGER_WORKING_DIRECTORY "${CMAKE_SOURCE_DIR}")