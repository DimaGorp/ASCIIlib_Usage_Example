project(FetchContent)

add_executable(Usage main.cpp)

include(FetchContent)

set(BRANCH_NAME "main" CACHE STRING "Branch name to fetch")
FetchContent_Declare(
    ASCII
    GIT_REPOSITORY https://github.com/DimaGorp/ASCIIlib.git
    GIT_TAG origin/${BRANCH_NAME}
    GIT_SHALLOW TRUE
    FIND_PACKAGE_ARGS
)

FetchContent_MakeAvailable(ASCII)

target_link_libraries(Usage PUBLIC ASCIIlib::Core)