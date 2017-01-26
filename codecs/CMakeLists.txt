
add_library(codec_opus_open_source SHARED codec_opus_open_source.c)
target_compile_definitions(codec_opus_open_source PRIVATE AST_MODULE=\"codec_opus_open_source\")
target_link_libraries(codec_opus_open_source opus)

install(TARGETS codec_opus_open_source DESTINATION "${AST_MOD_DIR}")

