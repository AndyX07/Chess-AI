# Chess-Engine

Chess Engine created in C++ using SDL2. The engine uses a **minimax algorithm** optimized with **alpha-beta pruning** for efficient move calculation.

## Technologies
- C++
- SDL2
- SDL2_image

## Requirements
Make sure you have **SDL2** and **SDL2_image** installed on your system.

### Windows
1. Download the SDL2 and SDL2_image development libraries.  
2. Provide the paths to your SDL2 installation **either by editing `CMakeLists.txt`**:

```cmake
# In CMakeLists.txt
set(SDL2_PATH "C:/Path/To/SDL2")
set(SDL2_IMAGE_PATH "C:/Path/To/SDL2_image")
```

**or by overriding them at configuration** when running CMake:

```bash
cmake -B build -S . -DSDL2_PATH="C:/Path/To/SDL2" -DSDL2_IMAGE_PATH="C:/Path/To/SDL2_image"
cmake --build build
```

3. Replace `"C:/Path/To/SDL2"` and `"C:/Path/To/SDL2_image"` with the paths where you installed SDL2 and SDL2_image.

## Building the Project
```bash
# Traditional method
mkdir build
cd build
cmake ..
cmake --build .

# Windows with path overrides
cmake -B build -S . -DSDL2_PATH="C:/Path/To/SDL2" -DSDL2_IMAGE_PATH="C:/Path/To/SDL2_image"
cmake --build build
```

![Screenshot](https://github.com/user-attachments/assets/744ea7d1-a0f0-4a61-a4a3-7d128fc2dac1)
