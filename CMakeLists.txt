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

include_directories("C:/Progra~1/ImageMagick-7.1.1-Q16-HDRI/include" "C:/Progra~1/SDL2")

add_library(ImageMagickWin SHARED "C:/Progra~1/ImageMagick-7.1.1-Q16-HDRI/include/Magick++.h")
add_library(SDL2 SHARED "C:/Progra~1/SDL2")

#target_include_directories(ImageMagickWin PUBLIC include/Magick++)
#target_include_directories(ImageMagickWin PUBLIC include/MagickCore)
#target_include_directories(ImageMagickWin PUBLIC include/MagickWand)

set_target_properties(ImageMagickWin PROPERTIES LINKER_LANGUAGE CXX)
set_target_properties(SDL2 PROPERTIES LINKER_LANGUAGE CXX)

target_link_libraries(Text_Visualizer LINK_PUBLIC GL)
target_link_libraries(Text_Visualizer LINK_PUBLIC ImageMagickWin)
target_link_libraries(Text_Visualizer LINK_PUBLIC SDL2)
