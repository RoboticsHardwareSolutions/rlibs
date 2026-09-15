cmake_minimum_required(VERSION 3.10)
project(BareMetalPLCPAL)

set(CMAKE_C_STANDARD 11)

add_subdirectory(rlibhelper)
add_subdirectory(runit)
add_subdirectory(rlog)
add_subdirectory(rtimeout)
add_subdirectory(rnode)
add_subdirectory(rbase64)
add_subdirectory(rbtn)
add_subdirectory(rbuffer)
add_subdirectory(rcrc)
add_subdirectory(rtimer)
add_subdirectory(rserial)
add_subdirectory(rstorage)
add_subdirectory(rproto)
add_subdirectory(rdebug)
add_subdirectory(rboot)

#add_subdirectory(rcan)




#FORMAT

# Create aggregate format target for all subprojects
add_custom_target(format_code
        COMMAND ${CMAKE_COMMAND} --build . --target rbase64_format
        COMMAND ${CMAKE_COMMAND} --build . --target rboot_format
        COMMAND ${CMAKE_COMMAND} --build . --target rbtn_format
        COMMAND ${CMAKE_COMMAND} --build . --target rbuffer_format
#        COMMAND ${CMAKE_COMMAND} --build . --target rcan_format
        COMMAND ${CMAKE_COMMAND} --build . --target rcrc_format
        COMMAND ${CMAKE_COMMAND} --build . --target rdebug_format
        COMMAND ${CMAKE_COMMAND} --build . --target rlog_format
        COMMAND ${CMAKE_COMMAND} --build . --target rnode_format
        COMMAND ${CMAKE_COMMAND} --build . --target rproto_format
        COMMAND ${CMAKE_COMMAND} --build . --target rserial_format
        COMMAND ${CMAKE_COMMAND} --build . --target rstorage_format
        COMMAND ${CMAKE_COMMAND} --build . --target rtimeout_format
        COMMAND ${CMAKE_COMMAND} --build . --target rtimer_format
        COMMAND ${CMAKE_COMMAND} --build . --target runit_format
        WORKING_DIRECTORY ${PROJECT_BINARY_DIR}
        COMMENT "Running clang-format on all source files"
)
























