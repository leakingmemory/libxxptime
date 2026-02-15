cmake_minimum_required(VERSION 4.1)
project(LibCppSharp)

include(GNUInstallDirs)

set(CMAKE_CXX_STANDARD 23)

add_library(xxptime SHARED DateOnly.cpp DateTime.cpp Duration.cpp TimeConst.cpp)

include_directories(xxptime ${CMAKE_CURRENT_SOURCE_DIR}/include/libxxptime)

set_target_properties(xxptime PROPERTIES SOVERSION 1 VERSION 1.0.0)

install(TARGETS xxptime
        LIBRARY DESTINATION ${CMAKE_INSTALL_LIBDIR}
        ARCHIVE DESTINATION ${CMAKE_INSTALL_LIBDIR}
        RUNTIME DESTINATION ${CMAKE_INSTALL_BINDIR}
)

install(DIRECTORY include/libxxptime DESTINATION "${CMAKE_INSTALL_INCLUDEDIR}")
