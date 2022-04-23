cmake_minimum_required(VERSION 3.0.0)

project(GTK_FindModule)

list(APPEND CMAKE_MODULE_PATH ${CMAKE_SOURCE_DIR}/cmake/modules)
find_package(GTK3 REQUIRED)

include_directories(${GTK3_INCLUDE_DIRS})
link_directories(${GTK3_LIBRARY_DIRS})

message("GTK_CFLAGS_OTHER" ${GTK_CFLAGS_OTHER})
add_definitions(${GTK_CFLAGS_OTHER})

add_executable(${PROJECT_NAME}_app main.cpp)

target_include_directories(${PROJECT_NAME}_app PRIVATE ${GTK3_INCLUDE_DIRS})
target_link_libraries(${PROJECT_NAME}_app PRIVATE ${GTK3_LIBRARIES})

message("GTK Include Directories: " ${GTK3_INCLUDE_DIRS})
message("GTK Libraries: " ${GTK3_LIBRARIES})