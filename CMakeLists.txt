
cmake_minimum_required(VERSION 3.20)

project(voyage LANGUAGES CXX)

add_executable(${PROJECT_NAME} demo.cpp)

# Both functions and macros the only difference is function is a normal function meanwhile a macro is basically a inline function

# functions

set (NAME "Arun")
set (EMP "SDE")

function (printMessage)
    foreach(var ${ARGN})
        message("${var} = ${${var}}")
    endforeach()
endfunction()

printMessage(PROJECT_NAME NAME EMP)

# macros

macro (printMacro)
    foreach (var ${ARGN})
        message("${var} = ${${var}}")
    endforeach()

    set (EMP "SDE-2")
endmacro()

printMacro(PROJECT_NAME NAME EMP CMAKE_CXX_COMPILER)
printMacro(PROJECT_NAME NAME EMP CMAKE_CXX_COMPILER)
