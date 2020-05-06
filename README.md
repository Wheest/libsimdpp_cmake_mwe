# SIMD CMake Dynamic Dispatch MWE

A minimum working example using the [libsimdpp](https://github.com/p12tic/libsimdpp) SIMD library, and the [CMake build system](https://cmake.org/).  It attempts to follow the dynamic dispatch example in the [docs](https://p12tic.github.io/libsimdpp/doc/html/index.html).

This repository uses git submodules, thus to build the repo, and run the example:

```
git clone --recurse-submodules https://github.com/Wheest/libsimdpp_cmake_mwe
cmake -H. -Bbuild
cmake --build build
```
