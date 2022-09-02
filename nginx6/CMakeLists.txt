cmake_minimum_required(VERSION 3.10.2)
project(nginx)
set(CMAKE_CXX_STANDARD 17)
file(GLOB SRC_FILES
    ${PROJECT_SOURCE_DIR}/app/*.cxx
    ${PROJECT_SOURCE_DIR}/signal/*.cxx
    ${PROJECT_SOURCE_DIR}/proc/*.cxx
    ${PROJECT_SOURCE_DIR}/net/*.cxx
    ${PROJECT_SOURCE_DIR}/misc/*.cxx
    ${PROJECT_SOURCE_DIR}/logs/*.cxx
    ${PROJECT_SOURCE_DIR}/logic/*.cxx
)

include_directories(${PROJECT_SOURCE_DIR}/_include/)

# ${PROJECT_SOURCE_DIR}
# message(STATUS ${SRC_FILES})
# message(STATUS ${PROJECT_SOURCE_DIR})

# c++标准库的多线程
# find_library(Threads REQUIRED)
set(EXECUTABLE_OUTPUT_PATH ${PROJECT_SOURCE_DIR}/bin)
add_executable(${PROJECT_NAME} ${SRC_FILES})
target_link_libraries(${PROJECT_NAME} pthread)

# target_link_libraries(${PROJECT_NAME} Threads::Threads)