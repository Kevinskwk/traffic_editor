cmake_minimum_required(VERSION 3.1.0)

project(traffic_editor)

find_package(yaml-cpp REQUIRED)

set(CMAKE_BUILD_TYPE RelWithDebInfo)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wall -Wshadow -Wextra")

set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)
set(CMAKE_AUTOUIC ON)

if(CMAKE_VERSION VERSION_LESS "3.7.0")
  set(CMAKE_INCLUDE_CURRENT_DIR ON)
endif()

find_package(Qt5 COMPONENTS Widgets REQUIRED)

add_executable(traffic-editor
  gui/add_param_dialog.cpp
  gui/building.cpp
  gui/building_dialog.cpp
  gui/building_level.cpp
  gui/building_level_dialog.cpp
  gui/building_level_table.cpp
  gui/edge.cpp
  gui/editor.cpp
  gui/editor_model.cpp
  gui/fiducial.cpp
  gui/layer.cpp
  gui/layer_dialog.cpp
  gui/level.cpp
  gui/lift.cpp
  gui/lift_dialog.cpp
  gui/lift_door.cpp
  gui/lift_table.cpp
  gui/main.cpp
  gui/map_view.cpp
  gui/model.cpp
  gui/model_dialog.cpp
  gui/param.cpp
  gui/polygon.cpp
  gui/preferences_dialog.cpp
  gui/preferences_keys.cpp
  gui/project.cpp
  gui/project_dialog.cpp
  gui/scenario.cpp
  gui/scenario_dialog.cpp
  gui/scenario_level.cpp
  gui/scenario_table.cpp
  gui/table_list.cpp
  gui/traffic_table.cpp
  gui/vertex.cpp
  gui/yaml_utils.cpp
  resources/resource.qrc
)

target_link_libraries(traffic-editor
  Qt5::Widgets
  yaml-cpp)

install(
  TARGETS traffic-editor
  LIBRARY DESTINATION lib
  RUNTIME DESTINATION bin
)
