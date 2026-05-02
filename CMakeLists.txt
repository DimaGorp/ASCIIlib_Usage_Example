cmake_minimum_required(VERSION 3.28)

add_executable(Usage main.cpp)

include(FetchContent)

FetchContent_Declare(
    ASCII
    GIT_REPOSITORY https://github.com/DimaGorp/ASCIIlib.git
    GIT_TAG origin/feature/CMake
    GIT_SHALLOW TRUE
    FIND_PACKAGE_ARGS
)

FetchContent_MakeAvailable(ASCII)

target_link_libraries(Usage PUBLIC ASCIIlib::Core)