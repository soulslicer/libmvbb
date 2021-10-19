cmake_minimum_required(VERSION 2.8.3)
project(mvbb)

file(GLOB mvbb_lib_SRC
    "*.cpp"
)
file(GLOB mvbb_lib_HDR
    "*.h"
)

find_package(Eigen3 REQUIRED)
include_directories(${EIGEN3_INCLUDE_DIR})
include_directories(
  ${CMAKE_CURRENT_SOURCE_DIR}
)

add_library(mvbb SHARED ${mvbb_lib_SRC})
target_link_libraries(mvbb)

install(TARGETS mvbb DESTINATION lib)
install(FILES ${mvbb_lib_HDR} DESTINATION include)
install(FILES LICENSE DESTINATION license)
