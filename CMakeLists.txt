cmake_minimum_required(VERSION 3.12)
project(cpp_app)

set(CMAKE_RUNTIME_OUTPUT_DIRECTORY "../bin")

find_package(PkgConfig REQUIRED)
pkg_check_modules(GTK3 REQUIRED gtk+-3.0)
include_directories(${GTK3_INCLUDE_DIRS})
link_directories(${GTK3_LIBRARY_DIRS})
add_definitions(${GTK3_CFLAGS_OTHER})

file(GLOB sourcefiles "src/*.h" "src/*.cpp")
add_executable(${PROJECT_NAME} ${sourcefiles}
)
target_link_libraries(cpp_app ${GTK3_LIBRARIES})


