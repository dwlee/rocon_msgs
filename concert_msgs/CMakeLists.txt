##############################################################################
# CMake
##############################################################################

cmake_minimum_required(VERSION 2.8.3)
project(concert_msgs)

##############################################################################
# Dependencies
##############################################################################

find_package(catkin REQUIRED COMPONENTS 
    gateway_msgs
    message_generation 
    rocon_app_manager_msgs
    rocon_std_msgs
    std_msgs
    uuid_msgs
)

##############################################################################
# Messgaes
##############################################################################

add_message_files(
  DIRECTORY msg
  FILES
  ConcertClient.msg
  ConcertClients.msg
  ConcertInfo.msg
  ConcertService.msg
  ConcertServices.msg
  Constants.msg
  ErrorCodes.msg
  InteractiveClient.msg
  InteractiveClients.msg
  LinkConnection.msg
  LinkEdge.msg
  LinkGraph.msg
  LinkNode.msg
  RemoconApp.msg
  RemoconStatus.msg
  RoleAppList.msg
  Roles.msg
  ServiceResourcePair.msg  # to be deprecated
  Strings.msg
)

add_service_files(
  DIRECTORY srv
  FILES
  GetApp.srv
  GetRolesAndApps.srv
  RequestInteraction.srv
  SetRolesAndApps.srv
  StartSolution.srv
  StopSolution.srv
  RemoveConcertService.srv
  ResourceStatus.srv  # to be deprecated
  EnableConcertService.srv
)

generate_messages(DEPENDENCIES
    gateway_msgs
    rocon_app_manager_msgs
    rocon_std_msgs
    std_msgs 
    uuid_msgs
)

##############################################################################
# Package
##############################################################################

catkin_package(CATKIN_DEPENDS 
                   gateway_msgs
                   message_runtime
                   rocon_app_manager_msgs
                   rocon_std_msgs
                   std_msgs
                   uuid_msgs
               )
