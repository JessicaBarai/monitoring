cmake_minimum_required(VERSION 3.6.2)

set(CMAKE_CXX_STANDARD 11)

#set( jaeger-client-cpp-0.7.0_DIR ${CMAKE_CURRENT_SOURCE_DIR}/../lib/jaeger-client-cpp-0.7.0)

#if ( CMAKE_SOURCE_DIR STREQUAL CMAKE_CURRENT_SOURCE_DIR )
#   add_subdirectory(${jaeger-client-cpp-0.7.0_DIR} ${jaeger-client-cpp-0.7.0_DIR})
#endif()

add_subdirectory(/volvo/edb/dev/code/allinone/jaeger-client-cpp-master /volvo/edb/dev/code/allinone/jaeger-client-cpp-master/build)



project(testproject)


find_package(prometheus-cpp CONFIG REQUIRED)
#find_package(jaegertracing CONFIG REQUIRED)


add_executable(${PROJECT_NAME} main.cpp)
target_link_libraries(${PROJECT_NAME} PRIVATE prometheus-cpp::pull PRIVATE jaegertracing)
#target_link_libraries(${PROJECT_NAME} PRIVATE jaegertracing)
