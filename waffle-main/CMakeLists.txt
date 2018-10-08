
add_executable(
    waffle-main
    main.cpp
)

target_link_libraries(waffle-main waffle-lib)

set_target_properties(waffle-main PROPERTIES VS_DEBUGGER_WORKING_DIRECTORY "${CMAKE_SOURCE_DIR}")

