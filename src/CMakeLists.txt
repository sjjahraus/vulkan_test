set(exe_name ${MAIN_PROJECT})

set(src_files
	main.cpp
)

source_group("Main" FILES ${src_files})
add_executable(${exe_name} 
	${src_files}
)

#set_target_properties(${exe_name} PROPERTIES DEBUG_POSTFIX ${CMAKE_DEBUG_POSTFIX})

target_include_directories(${exe_name} PRIVATE . ${STB_INCLUDE_DIRS} vendor/glfw/include vendor/glm vendor/volk)
target_link_directories(${exe_name} PRIVATE vendor/glfw/src vendor/glm vendor/volk)
target_link_libraries(${exe_name} PRIVATE glfw glm ${extra_libs} volk_headers)

add_dependencies(${exe_name} Assets)