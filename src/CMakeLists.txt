cmake_minimum_required(VERSION 3.12)

set(PICO_SDK_PATH "/home/aivree/Code/Pi_Pico/pico-sdk")

# Pull in SDK (must be before project)
include(${PICO_SDK_PATH}/external/pico_sdk_import.cmake)

project(AudioController C CXX ASM)
set(CMAKE_C_STANDARD 11)
set(CMAKE_CXX_STANDARD 17)

# Initialize the SDK
pico_sdk_init()

add_executable(audio_controller
        audio_controller.c
        usb_descriptors.c
        )

target_include_directories(audio_controller PRIVATE ${CMAKE_CURRENT_LIST_DIR})

target_link_libraries(audio_controller PRIVATE pico_stdlib tinyusb_device tinyusb_board)

pico_add_extra_outputs(audio_controller)

# add url via pico_set_program_url
# example_auto_set_url(audio_controller)
