cmake_minimum_required(VERSION 3.22.1)

project(main)

#find_package(armadillo)

add_executable(${PROJECT_NAME} main.cpp)

add_subdirectory(external/jsoncpp)

add_subdirectory(external/armadillo)

target_include_directories(${PROJECT_NAME} PUBLIC external/jsoncpp/include PUBLIC external/armadillo/include)

target_link_directories(${PROJECT_NAME} PUBLIC out/build2/lib)

target_link_libraries(${PROJECT_NAME} jsoncpp_lib armadillo)
