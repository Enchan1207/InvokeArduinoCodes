#
# InvokeArduinoLibs
#
cmake_minimum_required(VERSION 3.0)

set(ARDUINO_PACKAGE_ROOT "${ARDUINOCLI_ROOT}/packages/arduino/hardware/avr/1.8.5")

add_executable_avr(main)
target_sources(main PRIVATE
    ${ARDUINO_PACKAGE_ROOT}/cores/arduino/WInterrupts.c
    ${ARDUINO_PACKAGE_ROOT}/cores/arduino/hooks.c
    ${ARDUINO_PACKAGE_ROOT}/cores/arduino/wiring.c
    ${ARDUINO_PACKAGE_ROOT}/cores/arduino/wiring_analog.c
    ${ARDUINO_PACKAGE_ROOT}/cores/arduino/wiring_digital.c
    ${ARDUINO_PACKAGE_ROOT}/cores/arduino/wiring_pulse.S
    ${ARDUINO_PACKAGE_ROOT}/cores/arduino/wiring_pulse.c
    ${ARDUINO_PACKAGE_ROOT}/cores/arduino/wiring_shift.c
    
    ${ARDUINO_PACKAGE_ROOT}/cores/arduino/main.cpp
    
    InvokeArduinoLibs.cpp
)
target_include_directories(main PUBLIC
    ${ARDUINO_PACKAGE_ROOT}/variants/standard
    ${ARDUINO_PACKAGE_ROOT}/cores/arduino
)
