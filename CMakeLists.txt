cmake_minimum_required(VERSION 3.1)

project(lvgl_fb)
find_package(SDL2 REQUIRED)
include_directories(.)
add_subdirectory(lvgl)
add_subdirectory(lv_drivers)

add_executable(${PROJECT_NAME} main.c mouse_cursor_icon.c)
target_include_directories(${PROJECT_NAME} PRIVATE ${SDL2_INCLUDE_DIR})
target_link_libraries(${PROJECT_NAME} PRIVATE lvgl lvgl::drivers ${SDL2_LIBRARY})
