<<<<<<< HEAD
<<<<<<< HEAD
=======
>>>>>>> 5ae922dd597561775d9c7065a3dcd4920acf4251
cmake_minimum_required(VERSION 3.0)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

option(BUILD_EXAMPLES "Build examples" OFF)

project(print)

add_library(print STATIC ${CMAKE_CURRENT_SOURCE_DIR}/sources/print.cpp)

target_include_directories(print PUBLIC
  $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include>
  $<INSTALL_INTERFACE:include>
<<<<<<< HEAD
)

if(BUILD_EXAMPLES)
  file(GLOB EXAMPLE_SOURCES "${CMAKE_CURRENT_SOURCE_DIR}/examples/*.cpp")
  foreach(EXAMPLE_SOURCE ${EXAMPLE_SOURCES})
    get_filename_component(EXAMPLE_NAME ${EXAMPLE_SOURCE} NAME_WE)
    add_executable(${EXAMPLE_NAME} ${EXAMPLE_SOURCE})
    target_link_libraries(${EXAMPLE_NAME} print)
    install(TARGETS ${EXAMPLE_NAME}
      RUNTIME DESTINATION bin
    )
  endforeach(EXAMPLE_SOURCE ${EXAMPLE_SOURCES})
endif()

install(TARGETS print
    EXPORT print-config
    ARCHIVE DESTINATION lib
    LIBRARY DESTINATION lib
)

install(DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}/include/ DESTINATION include)
install(EXPORT print-config DESTINATION cmake)

option(BUILD_TESTS "Build tests" OFF)

if(BUILD_TESTS)
    enable_testing()
    file(GLOB CHECK ${PROJECT_NAME}_TEST_SOURCES "/tests/*.cpp")
    add_executable(check \${\${PROJECT_NAME}_TEST_SOURCES})
    target_link_libraries(check \${PROJECT_NAME} \${DEPENDS_LIBRARIES})
    add_test(NAME check COMMAND check "-s" "-r" "compact" "--use-colour" "yes") 
endif()
=======
add_executable (tests
main.cpp bar.cpp
)
>>>>>>> refs/remotes/origin/master
=======
)

if(BUILD_EXAMPLES)
  file(GLOB EXAMPLE_SOURCES "${CMAKE_CURRENT_SOURCE_DIR}/examples/*.cpp")
  foreach(EXAMPLE_SOURCE ${EXAMPLE_SOURCES})
    get_filename_component(EXAMPLE_NAME ${EXAMPLE_SOURCE} NAME_WE)
    add_executable(${EXAMPLE_NAME} ${EXAMPLE_SOURCE})
    target_link_libraries(${EXAMPLE_NAME} print)
    install(TARGETS ${EXAMPLE_NAME}
      RUNTIME DESTINATION bin
    )
  endforeach(EXAMPLE_SOURCE ${EXAMPLE_SOURCES})
endif()

install(TARGETS print
    EXPORT print-config
    ARCHIVE DESTINATION lib
    LIBRARY DESTINATION lib
)

install(DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}/include/ DESTINATION include)
install(EXPORT print-config DESTINATION cmake)

option(BUILD_TESTS "Build tests" OFF)

if(BUILD_TESTS)
    enable_testing()
    file(GLOB CHECK ${PROJECT_NAME}_TEST_SOURCES "/tests/*.cpp")
    add_executable(check \${\${PROJECT_NAME}_TEST_SOURCES})
    target_link_libraries(check \${PROJECT_NAME} \${DEPENDS_LIBRARIES})
    add_test(NAME check COMMAND check "-s" "-r" "compact" "--use-colour" "yes") 
endif()
>>>>>>> 5ae922dd597561775d9c7065a3dcd4920acf4251
