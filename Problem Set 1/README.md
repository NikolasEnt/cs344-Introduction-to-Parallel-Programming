# Problem Set 1

Convert color images into grayscale with CUDA.

## How to use
```bash
mkdir build
cd build
cmake ..
make
./HW1 path/to/the/input/image
```

The result image is outouted in the build directory.
The program prints out timing of execution in three modes: CUDA, straightforward loop and openCV conversion. The difference is more sound on big input images.

## Sample output

Input image:

![Original image](cinque_terre_small.jpg)

Output image:

![Output grayscale image](HW1_output.png)
