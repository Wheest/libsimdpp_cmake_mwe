cmake_minimum_required (VERSION 3.8)
project (SIMD_MWE)

set(CMAKE_MODULE_PATH "${CMAKE_SOURCE_DIR}/cmake/")
add_subdirectory(${PROJECT_SOURCE_DIR}/3rdparty/libsimdpp/ build)
list(APPEND Mwe_INCLUDE_DIRS PUBLIC ${PROJECT_SOURCE_DIR}/3rdparty/libsimdpp/)
list(APPEND Mwe_INCLUDE_DIRS PUBLIC ${PROJECT_SOURCE_DIR})

include_directories(${Mwe_INCLUDE_DIRS})

include(SimdppMultiarch)
simdpp_get_runnable_archs(RUNNABLE_ARCHS)
simdpp_multiarch(GEN_ARCH_FILES test.cpp ${RUNNABLE_ARCHS})
add_executable(test main.cpp ${GEN_ARCH_FILES})
target_link_libraries(test pthread)
set_target_properties(test PROPERTIES COMPILE_FLAGS "-std=c++11")
