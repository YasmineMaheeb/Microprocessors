cmake_minimum_required(VERSION 3.3)
project(Microprocessors C)
set(CMAKE_C_STANDARD 11)
find_package(MPI)
include_directories(SYSTEM ${MPI_INCLUDE_PATH})
add_executable(bcast bcast.c)
add_executable(serial serial.c)
add_executable(sendrec sendrec.c)
add_executable(sg scattergather.c)
target_link_libraries(bcast ${MPI_C_LIBRARIES})
target_link_libraries(sendrec ${MPI_C_LIBRARIES})
target_link_libraries(sg ${MPI_C_LIBRARIES})

