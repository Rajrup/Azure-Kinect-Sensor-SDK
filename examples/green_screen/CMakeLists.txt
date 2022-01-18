# Copyright (c) Microsoft Corporation. All rights reserved.
# Licensed under the MIT License.

if (OpenCV_FIND_REQUIRED)
	set (OpenCV_REQ_FLAG "REQUIRED")
else()
	set (OpenCV_REQ_FLAG)
endif()

if ("${CMAKE_SYSTEM_NAME}" STREQUAL "Windows")
	find_package (OpenCV CONFIG PATHS "C:/opencv/build/x64/vc14/lib" ${OpenCV_REQ_FLAG})
else()
	find_package (OpenCV CONFIG ${OpenCV_REQ_FLAG})
endif ()
add_executable(green_screen main.cpp)
target_link_libraries(green_screen PRIVATE k4a ${OpenCV_LIBS})
