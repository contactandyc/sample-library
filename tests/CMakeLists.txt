add_executable(sample_test src/test_hello.c)

target_link_libraries(sample_test PRIVATE ${PROJECT_NAME})

add_test(NAME hello COMMAND sample_test) 