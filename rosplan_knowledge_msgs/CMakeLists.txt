cmake_minimum_required(VERSION 2.8.3)
project(rosplan_knowledge_msgs)

## Find catkin macros and libraries
find_package(catkin REQUIRED COMPONENTS
  message_generation
  diagnostic_msgs
  roscpp
  rospy
  std_msgs
  geometry_msgs
  genmsg
)

## Generate messages in the 'msg' folder
add_message_files(
  FILES
  Filter.msg
  KnowledgeItem.msg
  Notification.msg
  DomainFormula.msg
  DomainOperator.msg
)

## Generate services in the 'srv' folder
add_service_files(
  FILES
  GetAttributeService.srv
  GetInstanceService.srv
  KnowledgeUpdateService.srv
  KnowledgeUpdateServiceArray.srv
  KnowledgeQueryService.srv
  GetDomainAttributeService.srv
  GetDomainTypeService.srv
  GetDomainOperatorService.srv  
  GetDomainOperatorDetailsService.srv  
  GetDomainPredicateDetailsService.srv  
  CreatePRM.srv
  AddWaypoint.srv
  GenerateProblemService.srv
)

## Generate added messages and services with any dependencies listed here
generate_messages(
  DEPENDENCIES
  geometry_msgs
  diagnostic_msgs
  std_msgs
)

## Declare things to be passed to dependent projects
catkin_package(
  CATKIN_DEPENDS message_generation message_runtime diagnostic_msgs geometry_msgs roscpp rospy std_msgs genmsg
)

###########
## Build ##
###########

include_directories(
  ${catkin_INCLUDE_DIRS}
)
