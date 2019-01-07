############################################################################
# <summary> CMakeLists.txt for OpenCV and CUDA. </summary>
# <date>    2018-12-27          </date>
# <author>  Quan Tran Minh. edit by Johannes Kast, Michael Sarahan, Nikolay Falaleev </author>
# <email>   quantm@unist.ac.kr  kast.jo@googlemail.com msarahan@gmail.com nikolasent@gmail.com</email>
############################################################################
cmake_minimum_required(VERSION 3.1 FATAL_ERROR)
project(HW2 LANGUAGES CXX CUDA)
find_package(OpenCV  REQUIRED)
find_package(CUDA  REQUIRED)
include_directories("${CUDA_INCLUDE_DIRS}")
# collect source files

file( GLOB  hdr *.hpp *.h )
file( GLOB  cu  *.cu)
set (HW2_files main.cpp reference_calc.cpp compare.cpp)
    
add_executable(HW2 ${HW2_files} ${hdr} ${cu})
target_link_libraries( HW2 ${OpenCV_LIBS})
