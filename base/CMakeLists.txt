file(GLOB BASE_SRC "*.cpp")
file(GLOB BASE_H "*.h")

message(STATUS "Searching for Vulkan")
find_package(Vulkan REQUIRED)

if(NOT Vulkan_FOUND)
	message(FATAL_ERROR "Vulkan not found.")
endif()

add_library(Base STATIC ${BASE_SRC} ${BASE_H})
target_link_libraries(Base Vulkan::Vulkan)
