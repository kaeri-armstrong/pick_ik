list(APPEND CMAKE_MODULE_PATH ${PROJECT_SOURCE_DIR}/cmake)

find_package(Catch2 3.3.0 REQUIRED)

add_executable(test-armstrong_pick_ik
    goal_tests.cpp
    ik_tests.cpp
    ik_memetic_tests.cpp
    robot_tests.cpp
)
target_link_libraries(test-armstrong_pick_ik
        PRIVATE
    armstrong_pick_ik_plugin
    Catch2::Catch2WithMain
    moveit_core::moveit_test_utils
)
catch_discover_tests(test-armstrong_pick_ik)
