# This file was generated by FRUT's Jucer2CMake from "guiapp6.jucer"

cmake_minimum_required(VERSION 3.12)

project("guiapp6")


find_package(JUCE CONFIG REQUIRED)


juce_add_gui_app(guiapp6
  VERSION "1.0.0"
  BUNDLE_ID "org.myorg.myapp"

  NEEDS_WEB_BROWSER TRUE
  PLUGINHOST_AU TRUE
)

juce_generate_juce_header(guiapp6)

target_compile_definitions(guiapp6
  PRIVATE
    JUCE_PLUGINHOST_AU=1
    JUCE_STRICT_REFCOUNTEDPOINTER=1
    JUCE_USE_CURL=0
    JUCE_WEB_BROWSER=1
)

target_sources(guiapp6
  PRIVATE
    "Source/Main.cpp"
    "Source/MainComponent.cpp"
)

juce_add_binary_data(guiapp6_BinaryData
  NAMESPACE "BinaryNamespace"
  SOURCES
    "Source/icons/16x16.png"
    "Source/icons/32x32.png"
)

target_link_libraries(guiapp6
  PRIVATE
    guiapp6_BinaryData
    juce::juce_audio_basics
    juce::juce_audio_processors
    juce::juce_core
    juce::juce_data_structures
    juce::juce_events
    juce::juce_graphics
    juce::juce_gui_basics
    juce::juce_gui_extra
  PUBLIC
    juce::juce_recommended_config_flags
    juce::juce_recommended_lto_flags
    juce::juce_recommended_warning_flags
)
