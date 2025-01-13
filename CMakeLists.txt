add_subdirectory(inc)

add_library(ecss)

file(GLOB_RECURSE ECSS_SOURCES "src/*.cpp" "src/Helpers/*.cpp" "src/Services/*.cpp" "src/Time/*.cpp")

target_sources(ecss PRIVATE ${ECSS_SOURCES})

target_include_directories(ecss PRIVATE inc)

target_link_libraries(ecss INTERFACE ecss_headers CAN_inc etl::etl PRIVATE CAN_inc CAN ecss_headers freertos_kernel etl::etl log_common)
