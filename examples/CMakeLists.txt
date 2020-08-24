# build a single example
function(buildExample EXAMPLE_NAME)
	set(EXAMPLE_FOLDER ${CMAKE_CURRENT_SOURCE_DIR}/${EXAMPLE_NAME})
	message(STATUS "Currently generating example in folder ${EXAMPLE_FOLDER}")
	file(GLOB SOURCE *.cpp)
	set(MAIN_CPP ${EXAMPLE_FOLDER}/${EXAMPLE_NAME}.cpp)
	if(EXISTS ${EXAMPLE_FOLDER}/${EXAMPLE_NAME}.h)
		set(MAIN_H ${EXAMPLE_FOLDER}/${EXAMPLE_NAME}.h)
	endif()
	add_executable(${EXAMPLE_NAME} ${MAIN_CPP} ${SOURCE})
	target_link_libraries(${EXAMPLE_NAME} Base)
	set_target_properties(${EXAMPLE_NAME} PROPERTIES VS_DEBUGGER_WORKING_DIRECTORY ${CMAKE_SOURCE_DIR}/bin)
endfunction(buildExample)

# list all examples
set(EXAMPLES
	Triangle 
)

# build all examples
function(buildAll)
	foreach(EXAMPLE ${EXAMPLES})
		buildExample(${EXAMPLE})
	endforeach(EXAMPLE)
endfunction(buildAll)

buildAll()
