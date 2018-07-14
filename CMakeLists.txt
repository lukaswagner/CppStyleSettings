if(MSVC)
    string(REPLACE "/" "\\" target_file "${CMAKE_CURRENT_SOURCE_DIR}/style.sln.DotSettings")
    string(REPLACE "/" "\\" link_file "${CMAKE_BINARY_DIR}/${CMAKE_PROJECT_NAME}.sln.DotSettings")

    if(NOT EXISTS ${link_file})
        message(STATUS "Setting up symlink for style settings...")
        message(STATUS "Target file: " ${target_file})
        message(STATUS "Link file: " ${link_file})
        
        execute_process(COMMAND cmd /c mklink /H "${link_file}" "${target_file}")
    endif()
endif()
