cmake_minimum_required(VERSION 3.0.0)

project(icp VERSION 0.1.0)

add_library(${PROJECT_NAME}
    include/icp.h
    # include/tr_icp.h
    src/icp.cpp
    # src/tr_icp.cpp
)

target_include_directories(${PROJECT_NAME}
    PUBLIC $<BUILD_INTERFACE:${CMAKE_CURRENT_LIST_DIR}/include>
)

find_package( OpenCV REQUIRED )
include_directories( ${OpenCV_INCLUDE_DIRS} )
target_link_libraries(${PROJECT_NAME} 
    PUBLIC ${OpenCV_LIBS}
)