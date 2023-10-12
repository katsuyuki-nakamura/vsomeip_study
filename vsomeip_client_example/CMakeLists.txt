cmake_minimum_required(VERSION 3.15)

project(
    client_example
    VERSION 0.1.0
    LANGUAGES CXX
)

find_package(vsomeip3 REQUIRED)
find_package(Boost COMPONENTS system thread log REQUIRED)

include_directories(
    $(Boost_INCLUDE_DIR)
    $(VSOMEIP_INCLUDE_DIRS)
)

message(STATUS "Current source directory is: ${CMAKE_CURRENT_SOURCE_DIR}")


add_executable(${PROJECT_NAME}
    ${CMAKE_CURRENT_SOURCE_DIR}/src/vsomeip_client_example.cpp
)

target_link_libraries(${PROJECT_NAME}
    vsomeip3
    ${Boost_LIBRARIES}
)
