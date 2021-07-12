cmake_minimum_required(VERSION 3.2 FATAL_ERROR)
project(LibTorch_inference)

#set(CMAKE_PREFIX_PATH "/home/lola/libtorch-shared-with-deps-latest/libtorch/share/cmake/Torch")
find_package(Torch REQUIRED PATHS "/home/lola/libtorch-shared-with-deps-latest/libtorch/share/cmake/Torch")

#set(CMAKE_PREFIX_PATH "/home/lola/LibTorch_inference/build")
find_package( OpenCV REQUIRED )

add_executable(LibTorch_inference LibTorch_inference.cpp)
target_link_libraries(LibTorch_inference ${TORCH_LIBRARIES} ${OpenCV_LIBS})
include_directories( ${OpenCV_INCLUDE_DIRS} )
#target_link_libraries( LibTorch_inference "${OpenCV_LIBS}")
set_property(TARGET LibTorch_inference PROPERTY CXX_STANDARD 14)
set(CMAKE_CXX_STANDARD 14)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
