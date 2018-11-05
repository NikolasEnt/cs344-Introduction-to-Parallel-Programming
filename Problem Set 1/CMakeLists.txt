############################################################################
# <summary> CMakeLists.txt for OpenCV and CUDA. </summary>
# <date>    2018-11-04          </date>
# <author>  Quan Tran Minh. edit by Johannes Kast, Michael Sarahan, Nikolay Falaleev </author>
# <email>   quantm@unist.ac.kr  kast.jo@googlemail.com msarahan@gmail.com nikolasent@gmail.com</email>
############################################################################
cmake_minimum_required(VERSION 3.1 FATAL_ERROR)
project(HW1 LANGUAGES CXX CUDA)
find_package(OpenCV  REQUIRED)
find_package(CUDA  REQUIRED)
include_directories("${CUDA_INCLUDE_DIRS}")
# collect source files

file( GLOB  hdr *.hpp *.h )
file( GLOB  cu  *.cu)
set (HW1_files main.cpp reference_calc.cpp compare.cpp)

add_executable(HW1 ${HW1_files} ${hdr} ${cu})
target_link_libraries( HW1 ${OpenCV_LIBS})
