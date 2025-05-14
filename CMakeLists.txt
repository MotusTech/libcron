cmake_minimum_required(VERSION 3.6)

project(top)
add_subdirectory(libcron)

option(BUILD_TEST "Build libcron tests" ON)
if(BUILD_TEST)
  add_subdirectory(test)
  add_dependencies(cron_test libcron)
endif()

install(TARGETS libcron DESTINATION lib)
install(DIRECTORY libcron/include/libcron DESTINATION include)
install(DIRECTORY libcron/externals/date/include/date DESTINATION include)

