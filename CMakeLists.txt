cmake_minimum_required(VERSION 3.24)
project(BareMetalPLCPAL
        LANGUAGES C
        DESCRIPTION
        "Collection of small, portable C libraries for embedded and host platforms")

set(CMAKE_C_STANDARD 11)

enable_testing()

#################### SUBPROJECTS #######################
set(RLIBS_SUBPROJECTS
        rlibhelper
        runit
        rlog
        rtimeout
        rnode
        rbase64
        rbtn
        rbuffer
        rcrc
        rtimer
        rserial
        rstorage
        rproto
#        rdebug
        rboot
        rcan  # disabled: mid-refactor (see earlier session work), build intentionally broken
)

foreach (lib ${RLIBS_SUBPROJECTS})
    add_subdirectory(${lib})
endforeach ()

#################### FORMAT SECTION #######################
add_custom_target(format_code COMMENT "Running clang-format on all source files")
foreach (lib ${RLIBS_SUBPROJECTS})
    if (TARGET ${lib}_format)
        add_custom_command(TARGET format_code POST_BUILD
                COMMAND ${CMAKE_COMMAND} --build . --target ${lib}_format
                WORKING_DIRECTORY ${PROJECT_BINARY_DIR})
    endif ()
endforeach ()
