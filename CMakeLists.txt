#files

file(GLOB EssexEngineNetworkDaemon_HEADERS
    "src/Daemons/NetworkDaemon/*.h"
)
file(GLOB EssexEngineNetworkDaemon_SRC
    ${EssexEngineNetworkDaemon_HEADERS}
    "src/Daemons/NetworkDaemon/*.cpp"
)

#setup headers

file(COPY ${EssexEngineNetworkDaemon_HEADERS} DESTINATION "${CMAKE_BINARY_DIR}/lib/include/EssexEngineNetworkDaemon/")

#setup build

add_library(EssexEngineNetworkDaemon SHARED ${EssexEngineNetworkDaemon_SRC})
target_link_libraries(EssexEngineNetworkDaemon EssexEngineCore)