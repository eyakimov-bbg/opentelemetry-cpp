include(GoogleTest)

add_executable(dynamic_load_test dynamic_load_test.cc)
target_link_libraries(
  dynamic_load_test ${GTEST_BOTH_LIBRARIES} ${CORE_RUNTIME_LIBS}
  ${CMAKE_THREAD_LIBS_INIT} opentelemetry_api)
target_link_libraries(dynamic_load_test ${CMAKE_DL_LIBS})
gtest_add_tests(
  TARGET dynamic_load_test
  TEST_PREFIX plugin.
  TEST_LIST dynamic_load_test)
