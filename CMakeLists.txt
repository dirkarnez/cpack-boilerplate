cmake_minimum_required(VERSION 3.14)

project(cpack-boilerplate)

set(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} -static")

add_executable(${PROJECT_NAME}
    "src/main.cpp"
)

# put ${PROJECT_NAME}, which is the .exe file "applications" 
# to "bin" folder inside the installer 
install(TARGETS ${PROJECT_NAME}
    RUNTIME
    DESTINATION bin
    COMPONENT applications
)

set(CPACK_GENERATOR "NSIS")

include(CPack)
