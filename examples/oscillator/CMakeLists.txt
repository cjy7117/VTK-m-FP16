##============================================================================
##  Copyright (c) Kitware, Inc.
##  All rights reserved.
##  See LICENSE.txt for details.
##
##  This software is distributed WITHOUT ANY WARRANTY; without even
##  the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR
##  PURPOSE.  See the above copyright notice for more information.
##============================================================================
cmake_minimum_required(VERSION 3.8...3.14 FATAL_ERROR)
project(Oscillator CXX)

#Find the VTK-m package
find_package(VTKm REQUIRED QUIET)

add_executable(Oscillator Oscillator.cxx)
target_link_libraries(Oscillator PRIVATE vtkm_filter)
vtkm_add_target_information(Oscillator
                            MODIFY_CUDA_FLAGS
                            DEVICE_SOURCES Oscillator.cxx)
