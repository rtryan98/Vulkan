cmake_minimum_required(VERSION 3.8...3.18 FATAL_ERROR)

set(NAME VulkanExamples)

project(${NAME}
	VERSION 1.0
	DESCRIPTION "Minimal Vulkan Examples"
	LANGUAGES CXX)

add_subdirectory(vendor)
add_subdirectory(examples)
