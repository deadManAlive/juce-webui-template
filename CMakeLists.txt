cmake_minimum_required(VERSION 3.20)

project(JUCE_WEBUI_PLUGIN VERSION 0.1.0)

set(CMAKE_CXX_STANDARD 20)

add_subdirectory(JUCE)

juce_add_plugin(juce_webui
        FORMATS VST3
        PRODUCT_NAME "JUCE+WebUI Plugin"
        VST3_CATEGORIES FX
        )

include_directories(include)
file(GLOB SOURCES "src/*.cpp")
target_sources(juce_webui PRIVATE ${SOURCES})

target_compile_definitions(juce_webui
        PUBLIC
            JUCE_WEB_BROWSER=1
            JUCE_USE_WIN_WEBVIEW2=1
            JUCE_VST3_CAN_REPLACE_VST2=0
            JUCE_DISPLAY_SPLASH_SCREEN=0
        )

target_link_libraries(juce_webui
        PRIVATE
            juce::juce_audio_utils
            juce::juce_dsp
        PUBLIC
            juce::juce_recommended_config_flags
            juce::juce_recommended_lto_flags
            juce::juce_recommended_warning_flags
        )

