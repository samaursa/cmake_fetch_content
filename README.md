# cmake_fetch_content
CMake example of how to use the new CMake 3.11 [FetchContent module](https://cmake.org/cmake/help/v3.11/module/FetchContent.html)

# Building

Simply run 
```
mkdir build
cd build
cmake ../
```
or 
```
mkdir build
cd build
cmake ../ -DFETCHCONTENT_QUIET=OFF
``` 
which is useful to see what `FetchContent` is doing.
