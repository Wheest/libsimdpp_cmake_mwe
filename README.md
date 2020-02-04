# SIMD CMake Dynamic Dispatch MWE

A minimum working example using the [libsimdpp](https://github.com/p12tic/libsimdpp) SIMD library, and the [CMake build system](https://cmake.org/).  It attempts to follow the dynamic dispatch example in the [docs](https://p12tic.github.io/libsimdpp/doc/html/index.html).

This repository uses git submodules, thus to build the repo, and run the example:

```
git clone --recurse-submodules https://github.com/Wheest/libsimdpp_cmake_mwe
mkdir -p libsimdpp_cmake_mwe/_build
cd libsimdpp_cmake_mwe/_build
cmake ..
make
./test
```

As it stands, the repo fails with error:

```
main.cpp:(.text+0x5): undefined reference to `print_arch()'
```

The CMake config does have the header file available to `main.cpp`, so it is unclear what the issue is.  The same code builds in the [Makefile example](https://github.com/p12tic/libsimdpp/tree/master/examples/dynamic_dispatch).
