cmake_minimum_required(VERSION 3.26)
project(Text_Visualizer)

set(CMAKE_CXX_STANDARD 17)

add_executable(Text_Visualizer main.cpp
        text_interpreter.cpp
        text_interpreter.h
        #   IMGUI Library Files
        imgui.h
        imgui.cpp
        imgui_demo.cpp
        imgui_draw.cpp
        imgui_tables.cpp
        imgui_widgets.cpp
        imstb_rectpack.h
        imstb_truetype.h
        imstb_textedit.h
        imgui_impl_sdl2.h
        imgui_impl_sdl2.cpp
        imgui_impl_opengl3.h
        imgui_impl_opengl3.cpp
        imgui_impl_opengl3_loader.h
)

target_link_libraries(Text_Visualizer SDL2 GL)
