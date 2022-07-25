# Created by Zhuoqun Chen
# on 2022-07-25 Monday 07:51

cmake_minimum_required(VERSION 3.14)

project(QtPropertyBrowserCMakeQt6
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


add_library(qtpropertybrowser STATIC

    # 8 sources
    qtpropertybrowser.cpp
    qtpropertymanager.cpp
    qteditorfactory.cpp
    qtvariantproperty.cpp
    qttreepropertybrowser.cpp
    qtbuttonpropertybrowser.cpp
    qtgroupboxpropertybrowser.cpp
    qtpropertybrowserutils.cpp

    # 8 headers
    qtpropertybrowser.h
    qtpropertymanager.h
    qteditorfactory.h
    qtvariantproperty.h
    qttreepropertybrowser.h
    qtbuttonpropertybrowser.h
    qtgroupboxpropertybrowser.h
    qtpropertybrowserutils_p.h

    # 1 qrc
    qtpropertybrowser.qrc
)
target_include_directories(qtpropertybrowser PRIVATE
    ${CMAKE_CURRENT_SOURCE_DIR}
)
target_link_libraries(qtpropertybrowser PRIVATE
    Qt6::Widgets
    Qt6::Core
    Qt6::Gui
)

add_subdirectory(examples)