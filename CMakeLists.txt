# Generated Cmake Pico project file

cmake_minimum_required(VERSION 3.13)

set(CMAKE_C_STANDARD 11)
set(CMAKE_CXX_STANDARD 17)

# Initialise pico_sdk from installed location
# (note this can come from environment, CMake cache etc)
set(PICO_SDK_PATH "/home/spencer/pico-sdk")

# Pull in Raspberry Pi Pico SDK (must be before project)
include(pico_sdk_import.cmake)

project(pico_neo_pixel C CXX ASM)

# Initialise the Raspberry Pi Pico SDK
pico_sdk_init()

# Add executable. Default name is the project name, version 0.1

add_executable(pico_neo_pixel pico_neo_pixel.c )

pico_set_program_name(pico_neo_pixel "pico_neo_pixel")
pico_set_program_version(pico_neo_pixel "0.1")

pico_enable_stdio_uart(pico_neo_pixel 0)
pico_enable_stdio_usb(pico_neo_pixel 1)

# Add the standard library to the build
target_link_libraries(pico_neo_pixel pico_stdlib)

# Add any user requested libraries
target_link_libraries(pico_neo_pixel
        hardware_dma
        hardware_pio
        hardware_interp
        hardware_timer
        hardware_watchdog
        hardware_clocks
        )

pico_add_extra_outputs(pico_neo_pixel)

