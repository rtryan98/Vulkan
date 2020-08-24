# add_subdirectory(vendor)

cmake_minimum_required(VERSION 3.13...3.18 FATAL_ERROR)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(NAME VulkanExamples)

project(${NAME}
	VERSION 1.0
	DESCRIPTION "Vulkan Examples"
	)

set(CMAKE_RUNTIME_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/bin/")

add_subdirectory(base)
add_subdirectory(examples)
