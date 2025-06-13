cmake_minimum_required(VERSION 3.10)
project(BareMetalPLCPAL)

set(CMAKE_C_STANDARD 11)

add_subdirectory(runit)
add_subdirectory(rbuffer)
add_subdirectory(rcrc)
add_subdirectory(rbase64)
add_subdirectory(rserial)
add_subdirectory(rstorage)
add_subdirectory(rtimeout)
add_subdirectory(rtimer)

#add_subdirectory(rbtn)
#add_subdirectory(rboot)
#add_subdirectory(rcan)
#add_subdirectory(rdebug)
#add_subdirectory(rlog)
#add_subdirectory(rnode)
#add_subdirectory(rproto)
#add_subdirectory(rtelnet)














