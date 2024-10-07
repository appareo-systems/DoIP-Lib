########################################################################
#
# Requirements and dependencies:

cmake_minimum_required(VERSION 3.14)
project(DoIP_Lib)

set(CMAKE_CXX_STANDARD 14)
# Enable 'rdyamic' switch to export the executable's symbols for debugging
set(CMAKE_ENABLE_EXPORTS 1)


########################################################################
#
# Options:

########################################################################
#
# Include Directory:

set(include_dir
  "${PROJECT_SOURCE_DIR}/include")

# Source Directory:

set(source_dir
  "${PROJECT_SOURCE_DIR}/src")



########################################################################

include_directories(${include_dir})

add_library(
  doip_lib
  ${source_dir}/message.cpp
  ${source_dir}/generic_nack.cpp
  ${source_dir}/vehicle_id_request.cpp
  ${source_dir}/eid_vehicle_id_request.cpp
  ${source_dir}/vin_vehicle_id_request.cpp
  ${source_dir}/vehicle_id_response.cpp
  ${source_dir}/routing_activation_request.cpp
  ${source_dir}/routing_activation_response.cpp
  ${source_dir}/alive_check_request.cpp
  ${source_dir}/alive_check_response.cpp
  ${source_dir}/power_mode_request.cpp
  ${source_dir}/power_mode_response.cpp
  ${source_dir}/entity_status_request.cpp
  ${source_dir}/entity_status_response.cpp
  ${source_dir}/diag_message.cpp
  ${source_dir}/diag_message_ack.cpp
  ${source_dir}/diag_message_nack.cpp
  ${source_dir}/announcement_timer.cpp
  ${source_dir}/doip_controller.cpp
)

target_include_directories(doip_lib
  INTERFACE ${include_dir}
)

