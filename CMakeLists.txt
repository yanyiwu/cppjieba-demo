CMAKE_MINIMUM_REQUIRED (VERSION 3.5)
PROJECT(CPPJIEBA-DEMO)

include(FetchContent)

FetchContent_Declare(cppjieba
    GIT_REPOSITORY https://github.com/yanyiwu/cppjieba.git
    GIT_TAG master
)
FetchContent_MakeAvailable(cppjieba)

# Add these lines to set up include directories
include_directories(${cppjieba_SOURCE_DIR}/include ${cppjieba_SOURCE_DIR}/deps/limonp/include)

if(NOT DEFINED CMAKE_CXX_STANDARD)
    set(CMAKE_CXX_STANDARD 11)
endif()
ADD_DEFINITIONS(-O3 -Wall -g)
ADD_EXECUTABLE(demo demo.cpp)
enable_testing()
ADD_TEST(NAME ./demo COMMAND ./demo)
