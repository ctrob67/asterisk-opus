
add_library(res_format_attr_opus SHARED res_format_attr_opus.c)
target_compile_definitions(res_format_attr_opus PRIVATE AST_MODULE=\"res_format_attr_opus\")
target_link_libraries(res_format_attr_opus opus)

install(TARGETS res_format_attr_opus res_format_attr_opus DESTINATION "${AST_MOD_DIR}")

