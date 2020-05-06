cmake_minimum_required (VERSION 3.8)
project (SIMD_MWE)

set(SIMDPP_DIR "${PROJECT_SOURCE_DIR}/3rdparty/libsimdpp")
set(CMAKE_MODULE_PATH "${SIMDPP_DIR}/cmake")
include_directories(${SIMDPP_DIR})

include(SimdppMultiarch)
simdpp_get_runnable_archs(RUNNABLE_ARCHS)
simdpp_multiarch(GEN_ARCH_FILES test.cpp ${RUNNABLE_ARCHS})
add_executable(simd_mwe main.cpp ${GEN_ARCH_FILES})
target_link_libraries(simd_mwe pthread)
set_target_properties(simd_mwe PROPERTIES COMPILE_FLAGS "-std=c++11")
