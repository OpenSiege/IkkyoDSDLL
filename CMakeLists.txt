cmake_minimum_required(VERSION 3.11)

project(ikkyo-dsdll)

set(SOURCE_FILES
	ikkyo.cpp
)

add_library(ikkyo SHARED ${SOURCE_FILES})

set_target_properties(ikkyo PROPERTIES SUFFIX ".dsdll")

set(CMAKE_CXX_FLAGS_RELEASE "${CMAKE_CXX_FLAGS_RELEASE} /MT /Zc:wchar_t-")
set(CMAKE_CXX_FLAGS_DEBUG "${CMAKE_CXX_FLAGS_DEBUG} /MTd /Zc:wchar_t-")

target_include_directories(ikkyo PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})