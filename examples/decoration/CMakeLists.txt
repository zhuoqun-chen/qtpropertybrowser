# Created by Zhuoqun Chen
# on 2022-07-25 Monday 07:51
cmake_minimum_required(VERSION 3.14)

project(decoration
	LANGUAGES CXX
	VERSION 0.1
)

set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

set(CMAKE_PREFIX_PATH F:\\Qt\\6.2.4\\msvc2019_64)
set(Qt6_DIR F:\\Qt\\6.2.4\\msvc2019_64\\lib\\cmake\\Qt6)
find_package(Qt6 REQUIRED COMPONENTS 
    Widgets 
    Core 
    Gui
)

add_executable(decoration WIN32
    main.cpp
)
target_include_directories(decoration PRIVATE
    ${CMAKE_CURRENT_SOURCE_DIR}
    ../../.
)
target_link_libraries(decoration PRIVATE

    qtpropertybrowser

    Qt6::Widgets
    Qt6::Core
    Qt6::Gui
)