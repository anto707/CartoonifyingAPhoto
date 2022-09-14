cmake_minimum_required(VERSION 3.8)

project(Toonify)

set(CMAKE_CXX_FLAGS "-fdiagnostics-color=always -std=c++11 -pthread -O3 -g -fPIC")

set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}/)

add_library(uwimg++ SHARED
		src/image.h
            src/load_image.cpp
            src/stb_image.h
			src/filter_image.cpp
            src/stb_image_write.h
            src/process_image.cpp
			src/resize_image.cpp

			src/median_filter.cpp
			src/canny.cpp
			src/dilation.cpp
			src/bilateral_filter.cpp
        )

link_libraries(uwimg++ m stdc++)

add_executable(main src/main/main.cpp)



