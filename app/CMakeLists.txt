#
# InvokeArduinoLibs
#
cmake_minimum_required(VERSION 3.0)

# load AVR toolchain
set(CMAKE_TOOLCHAIN_FILE "${CMAKE_SOURCE_DIR}/cmake/avr_toolchain.cmake")

# configure MCU
set(AVR_MCU "atmega328p")
set(AVRDUDE_MCU "m328p")
set(AVR_FCPU 16000000)

# configure programmer
set(AVRDUDE_PROGRAMMER "avrisp")
set(AVRDUDE_BAUDRATE 19200)

# Project configuration
project(InvokeArduinoLibs
    VERSION 0.1.0
    DESCRIPTION "Invoke Arduino libraries from CMake-with-AVR"
    LANGUAGES C CXX ASM
)

# source directory
add_subdirectory(src)