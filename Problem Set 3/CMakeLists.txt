############################################################################
# <summary> CMakeLists.txt for OpenCV and CUDA. </summary>
# <date>    2019-01-20          </date>
# <author>  Quan Tran Minh. edit by Johannes Kast, Michael Sarahan, Nikolay Falaleev</author>
# <email>   quantm@unist.ac.kr  kast.jo@googlemail.com msarahan@gmail.com nikolasent@gmail.com</email>
############################################################################
cmake_minimum_required(VERSION 3.1 FATAL_ERROR)
project(HW3 LANGUAGES CXX CUDA)
find_package(OpenCV  REQUIRED)
find_package(CUDA  REQUIRED)
include_directories("${CUDA_INCLUDE_DIRS}")

SET (compare_files compare.cpp)

file( GLOB  hdr *.hpp *.h )
file( GLOB  cu  *.cu)
set (HW3_files main.cpp loadSaveImage.cpp reference_calc.cpp compare.cpp)

add_executable(HW3 ${HW3_files} ${hdr} ${cu})
target_link_libraries( HW3 ${OpenCV_LIBS})
