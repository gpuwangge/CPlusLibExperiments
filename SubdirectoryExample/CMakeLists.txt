cmake_minimum_required(VERSION 3.5)
SET(CMAKE_C_COMPILER "C:/mingw64/bin/gcc.exe")
SET(CMAKE_CXX_COMPILER "C:/mingw64/bin/g++.exe")
project(testbench)
set(CMAKE_BUILD_TYPE "Debug")

include_directories(
    ${PROJECT_SOURCE_DIR}/model/include
)

link_directories(

)

add_subdirectory(model)
link_libraries(model-library)

############################################################
# Create a library
############################################################

#Generate the shared library from the library sources
#add_library(hello_library SHARED 
#    src/Hello.cpp
#)
#add_library(hello::library ALIAS hello_library)

#target_include_directories(hello_library
#    PUBLIC 
#        ${PROJECT_SOURCE_DIR}/include
#)

############################################################
# Create an executable
############################################################

# Add an executable with the above sources
add_executable(testbench_binary
    src/main.cpp
)

# link the new hello_library target with the hello_binary target
#target_link_libraries( hello_binary
#    PRIVATE 
#        hello::library
#)