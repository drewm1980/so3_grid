cmake_minimum_required(VERSION 2.8.12.2)
project(so3_grid)

set (CMAKE_CXX_FLAGS "-std=c++11")

if(NOT CMAKE_BUILD_TYPE)
	set(CMAKE_BUILD_TYPE "RelWithDebInfo" CACHE STRING
		"Choose the type of build, options are: Debug Release RelWithDebInfo MinSizeRel."
		FORCE)
endif(NOT CMAKE_BUILD_TYPE)

add_library(so3_grid mk_pix2xy.c  nside2npix.c  pix2ang_nest.c grid_s1.cpp  hopf2quat.cpp  layered_grid.cpp  main.cpp  simple_grid.cpp)

add_executable(generate_grid main.cpp)
target_link_libraries(generate_grid so3_grid)
