cmake_minimum_required(VERSION 2.8)

project(glv)

find_package(OpenGL REQUIRED)
find_package(GLUT REQUIRED)
find_package(GLEW REQUIRED)

include_directories(include)
include_directories(${OPENGL_INCLUDE_DIR})
include_directories(${GLUT_INCLUDE_DIRS})
include_directories(${GLEW_INCLUDE_DIRS})

set(SOURCES
  src/glv_sliders.cpp
  src/glv_model.cpp
  src/glv_color.cpp
  src/glv_glv.cpp
  src/glv_plots.cpp
  src/glv_grid.cpp
  src/glv_view.cpp
  src/glv_texture.cpp
  src/glv_draw.cpp
  src/glv_inputdevice.cpp
  src/glv_buttons.cpp
  src/glv_binding_glut.cpp
  src/glv_util.cpp
  src/glv_core.cpp
  src/glv_font.cpp
  src/glv_view3D.cpp
  src/glv_textview.cpp
  src/glv_widget.cpp
  src/glv_binding.cpp
  src/glv_layout.cpp
)

set(EXAMPLES
  densityPlot
  stretchAnchor
  notification
  grid
  spinSynth
  views
  dataPlot
  tableLayout
  spaceCurve
  attachVariable
  paintSimple
  presets
  scope
  paintDiffusion
  paintWave
  drawText
  soaring
  graphicsData
)

add_library(${PROJECT_NAME} ${SOURCES})

foreach(NAME ${EXAMPLES})
  add_executable(${PROJECT_NAME}_${NAME} examples/${NAME}.cpp)
  target_link_libraries(${PROJECT_NAME}_${NAME} ${PROJECT_NAME} ${OPENGL_LIBRARIES} ${GLEW_LIBRARIES} ${GLUT_LIBRARIES})
endforeach()
