
add_library(format_ogg_opus_open_source SHARED format_ogg_opus_open_source.c)
target_compile_options(format_ogg_opus_open_source PRIVATE -isystem =/usr/include/opus)
target_compile_definitions(format_ogg_opus_open_source PRIVATE AST_MODULE=\"format_ogg_opus_open_source\")
target_link_libraries(format_ogg_opus_open_source opus opusfile)

add_library(format_vp8 SHARED format_vp8.c)
target_compile_definitions(format_vp8 PRIVATE AST_MODULE=\"format_vp8\")

install(TARGETS format_vp8 DESTINATION "${AST_MOD_DIR}")

