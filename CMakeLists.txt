# Basic setup
cmake_minimum_required(VERSION 3.16.0)
project(Oil_Spill_Simulation)

set(CMAKE_CXX_STANDARD 14)

# Add all executables
add_executable(Oil_Spill_Simulation
        src/parameters/parameters.cpp
        src/parameters/parameters.h
        src/run.cpp
        src/parameters/simulation_parameters.h
        src/parameters/simulation_parameters.cpp
        src/simulation/render/window.cpp
        src/simulation/render/window.h
        src/simulation/camera/camera.cpp
        src/simulation/camera/camera.h
        src/simulation/helper/open_gl_helper.cpp
        src/simulation/helper/open_gl_helper.h
        src/fluids/fluids_solver.cpp
        src/fluids/fluids_solver.h src/simulation/render/fluids_window.cpp src/simulation/render/fluids_window.h)

# Include all directories
include_directories(.)
include_directories(src)
include_directories(src/parameters)
include_directories(src/simulation/render)
include_directories(src/simulation/camera)
include_directories(src/simulation/helper)
include_directories(src/fluids)


# Add OpenGL and GLUT packages
find_package(OpenGL REQUIRED)
find_package(GLUT REQUIRED)
include_directories( ${OPENGL_INCLUDE_DIRS}  ${GLUT_INCLUDE_DIRS} )
target_link_libraries(Oil_Spill_Simulation ${OPENGL_LIBRARIES} ${GLUT_LIBRARY} )

# File system
target_link_libraries(Oil_Spill_Simulation stdc++fs)

# JSON
include_directories(src/lib/json/include)


