# Set the source files to compile
file(GLOB file_source
    "src/*.h" "src/*.cpp" "src/*.hpp"
)
get_filename_component(app_target_name ${CMAKE_CURRENT_LIST_DIR} NAME)
set(app_ide_folder ${samples_dir_name}/${app_target_name})
source_group(TREE ${CMAKE_CURRENT_SOURCE_DIR} FILES ${file_source})


add_executable(${app_target_name} ${file_source})


target_link_libraries(${app_target_name}
        PRIVATE

    )


