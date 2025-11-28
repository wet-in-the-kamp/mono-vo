cmake_minimum_required(VERSION 2.8)
project( mono-vo )
find_package( OpenCV 3.0 REQUIRED )

include_directories( ${OpenCV_INCLUDE_DIRS} )

# Set compiler flags for profiling
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -pg")

file(GLOB viso
    "src/*.h"
    "src/*.cpp"
)
add_executable( vo ${viso} )
target_link_libraries( vo ${OpenCV_LIBS} )
