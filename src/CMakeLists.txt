# 查找当前目录下的所有源文件,并将名称保存到 SRC_LIST变量
# aux_source_directory只要CMakeLists文件不变，aux_source_directory就不会作用于新的文件中

aux_source_directory(. SRC_LIST)

#set(SRC_LIST 
#    Connection.cpp
#    CommonConnectionPool.cpp)

add_executable(connpool ${SRC_LIST})

#muduo_net是网络的核心模块 要放在前面 mt是多线程版本
target_link_libraries(connpool -lmysqlclient pthread)
