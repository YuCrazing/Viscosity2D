cmake_minimum_required(VERSION 3.1...3.25)

project(
  viscosity_paper
  VERSION 1.0
  LANGUAGES CXX)

# OpenGL && GLUT
find_package(OpenGL REQUIRED)
find_package(GLUT REQUIRED)

aux_source_directory(. CPP_SOURCES)

add_executable(viscosity ${CPP_SOURCES})

target_include_directories(viscosity
PRIVATE
  ${CMAKE_CURRENT_SOURCE_DIR}
)
target_include_directories(viscosity
PRIVATE
  ${OPENGL_INCLUDE_DIRS}
)
target_include_directories(viscosity
PRIVATE
  ${GLUT_INCLUDE_DIRS}
)

target_link_libraries(viscosity ${OPENGL_LIBRARIES} ${GLUT_LIBRARIES})