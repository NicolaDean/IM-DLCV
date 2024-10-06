#https://cmake.org/cmake/help/latest/guide/tutorial/Adding%20a%20Library.html

cmake_minimum_required(VERSION 3.10)
project(cvsandbox)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# glfw
find_package(glfw3 REQUIRED)
include_directories(${GLFW_INCLUDE_DIRS})
link_libraries(${GLFW_LIBRARY_DIRS})

# opengl
find_package(OpenGL REQUIRED)
include_directories(${OPENGL_INCLUDE_DIRS})

# glew
find_package(GLEW REQUIRED)
include_directories(${GLEW_INCLUDE_DIRS})

# opencv
find_package(OpenCV REQUIRED)
include_directories(${OpenCV_INCLUDE_DIRS})

# Include directories for ImGui
set(IMGUI_LIB /home/nicomane/Desktop/Programming/IM-DLCV/im-dlcv/imgui)
add_subdirectory(${IMGUI_LIB})

# Include the precompiled header lib
set(PCH_LIB /home/nicomane/Desktop/Programming/IM-DLCV/im-dlcv/pch)
add_subdirectory(${PCH_LIB})
include_directories(/home/nicomane/Desktop/Programming/IM-DLCV/vendor/imgui)
include_directories(/home/nicomane/Desktop/Programming/IM-DLCV/vendor/imgui/backends)

# Add the main executable
add_executable(${PROJECT_NAME} main2.cpp)

# Link libraries
target_link_libraries(${PROJECT_NAME} ${OPENGL_LIBRARIES} glfw ${OpenCV_LIBS} ${CMAKE_DL_LIBS} imgui dlcv_pch)
target_include_directories(${PROJECT_NAME} PUBLIC ${IMGUI_FOLDER})