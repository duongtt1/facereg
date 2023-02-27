cmake_minimum_required(VERSION 3.05)
project(facerec_ncnn)

set(CMAKE_CXX_STANDARD 14)

set(ncnn_DIR "/home/duoq/ncnn/build/install/lib/cmake/ncnn")
set(OpenCV_DIR "/home/duoq/app/lib/cmake/opencv4")


find_package(ncnn REQUIRED)

find_package(OpenCV REQUIRED)

include_directories(./)

file(GLOB HEAD ${CMAKE_CURRENT_SOURCE_DIR}/include/*.h)
file(GLOB SRCS ${CMAKE_CURRENT_SOURCE_DIR}/src/*.cpp)

include_directories(
    ${CMAKE_CURRENT_SOURCE_DIR}/include/
)

add_executable(${PROJECT_NAME} ${SRCS})

target_link_libraries(${PROJECT_NAME} ncnn ${OpenCV_LIBS})