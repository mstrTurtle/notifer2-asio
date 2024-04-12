# https://github.com/alexott/boost-asio-examples/blob/master/CMakeLists.txt
# 从Boost.Asio Example这个地方摘来的。

cmake_minimum_required(VERSION 3.15)
project(notifer2-asio LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSION ON)

set(CMAKE_BUILD_TYPE Debug)

set(Boost_INCLUDE_DIR "C:\\boost_1_85_0")

set(BOOST_ENABLE_CMAKE ON)
find_package(Boost REQUIRED)
LINK_DIRECTORIES(${Boost_LIBRARY_DIRS})
SET(USED_LIBS ${Boost_SYSTEM_LIBRARY} ${Boost_THREAD_LIBRARY} ${Boost_REGEX_LIBRARY})

add_executable(notifer2-asio notifer2-asio.cpp
api/api.cpp
loop/loop.cpp)
target_link_libraries(notifer2-asio ${USED_LIBS})
include_directories(${Boost_INCLUDE_DIRS}) 