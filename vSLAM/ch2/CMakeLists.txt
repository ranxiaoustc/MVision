# 声明cmake的最低版本
cmake_minimum_required( VERSION 2.8)

#声明一个cmake工程　名为　HelloSLAM
project( HelloSLAM)

#设置为Debug模式
set(CMAKE_BUILD_TYPE "Debug")
#添加一个库文件
#语法　静态库　add_library(hello libHelloSLAM.cpp)
add_library(hello libHelloSLAM.cpp)
#共享库
add_library( hello_shared SHARED libHelloSLAM.cpp)
#引用　了库的　可执行文件
add_executable(useHello useHelloSLAM.cpp)
#链接到库
target_link_libraries(useHello hello_shared)


#添加一个可执行程序　和　源程序名
#语法　add_executable( helloSLAM helloSLAM.cpp)
add_executable( helloSLAM helloSLAM.cpp)
