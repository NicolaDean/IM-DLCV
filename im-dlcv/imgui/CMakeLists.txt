#https://cmake.org/cmake/help/latest/command/target_precompile_headers.html
set(IMGUI_FOLDER /home/nicomane/Desktop/Programming/IM-DLCV/vendor/imgui)

# Include directories for ImGui
include_directories(${IMGUI_FOLDER})
include_directories(${IMGUI_FOLDER}/backends)

add_library(imgui STATIC
    ${IMGUI_FOLDER}/imgui.cpp
    ${IMGUI_FOLDER}/imgui_draw.cpp
    ${IMGUI_FOLDER}/imgui_widgets.cpp
    ${IMGUI_FOLDER}/imgui_tables.cpp
    ${IMGUI_FOLDER}/backends/imgui_impl_glfw.cpp
    ${IMGUI_FOLDER}/backends/imgui_impl_opengl3.cpp
)

target_link_libraries(imgui PUBLIC ${CMAKE_DL_LIBS})
target_include_directories(imgui PUBLIC ${CMAKE_CURRENT_SOURCE_DIR} )