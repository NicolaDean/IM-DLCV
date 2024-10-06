#https://cmake.org/cmake/help/latest/command/target_precompile_headers.html
set(PCH_FOLDER /home/nicomane/Desktop/Programming/IM-DLCV/im-dlcv/pch)

# Include directories for ImGui
include_directories(${PCH_FOLDER})

add_library(dlcv_pch STATIC
    ${PCH_FOLDER}/dlcv_pch.cpp
)

target_include_directories(dlcv_pch PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})