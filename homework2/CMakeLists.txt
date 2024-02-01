cmake_minimum_required( VERSION 3.12 )
project( jordan VERSION 1.0 )

# https://cmake.org/cmake/help/latest/module/FindMPI.html
find_package( MPI )

add_executable( jordan jordan.c )
target_include_directories(
	jordan PUBLIC
	${MPI_C_INCLUDE_DIRS} ${CMAKE_CURRENT_SOURCE_DIR} )
target_link_libraries(
	jordan PUBLIC 
	${MPI_C_LIBRARIES} )

install( TARGETS jordan DESTINATION . )
