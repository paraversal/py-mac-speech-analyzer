cmake_minimum_required(VERSION 3.26)
project(macspeechanalyzer LANGUAGES Swift)

add_library(macspeechanalyzer_core SHARED
    swift/core.swift
    swift/bridge.swift)

# Every build (wheel and editable redirect) installs into the build tree, so
# the source tree never receives compiled artifacts.
install(TARGETS macspeechanalyzer_core
        LIBRARY DESTINATION macspeechanalyzer
        RUNTIME DESTINATION macspeechanalyzer)