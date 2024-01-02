#只要cmakelist不变编译就不会变化，需删除build下的cmakefiles
#aux_source_directory(. SRC_LIST)

#这个调成静态库，因为muduo是静态的
set(SRC_LIST 
    mprpcapplication.cc 
    mprpcconfig.cc 
    rpcheader.pb.cc 
    rpcprovider.cc 
    mprpcchannel.cc
    mprpccontroller.cc
    logger.cc
    zookeeperutil.cc)
add_library(mprpc ${SRC_LIST})
target_link_libraries(mprpc muduo_net muduo_base pthread zookeeper_mt)#mt是多线程版本