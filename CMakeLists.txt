cmake_minimum_required(VERSION 4.1)
project(LibCppSharp)

set(CMAKE_CXX_STANDARD 23)

add_library(cppsharp SHARED DateOnly.cpp DateTime.cpp Duration.cpp TimeConst.cpp)

include_directories(cppsharp ${CMAKE_CURRENT_SOURCE_DIR}/include/libcppsharp)

set_target_properties(cppsharp PROPERTIES SOVERSION 1 VERSION 1.0.0)

install(TARGETS cppsharp
        LIBRARY DESTINATION ${CMAKE_INSTALL_LIBDIR}
        ARCHIVE DESTINATION ${CMAKE_INSTALL_LIBDIR}
        RUNTIME DESTINATION ${CMAKE_INSTALL_BINDIR}
)

install(DIRECTORY include DESTINATION "${CMAKE_INSTALL_INCLUDEDIR}")
