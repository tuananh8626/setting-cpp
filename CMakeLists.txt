cmake_minimum_required(VERSION 3.16)
project(MyCppProject LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 23)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

enable_testing()

add_executable(main src/main.cpp)
add_executable(sample_test tests/sample_test.cpp)

find_package(GTest REQUIRED)
target_link_libraries(sample_test GTest::gtest_main)

include(GoogleTest)
gtest_discover_tests(sample_test)
