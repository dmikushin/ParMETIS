# Include directories for library code.
include_directories(.)

# Find sources.
file(GLOB parmetis_sources *.c)

# Create libparmetis
add_library(parmetis ${ParMETIS_LIBRARY_TYPE} ${parmetis_sources})
target_link_libraries(parmetis MPI::MPI_C metis GKlib)

install(TARGETS parmetis
  LIBRARY DESTINATION lib
  RUNTIME DESTINATION lib
  ARCHIVE DESTINATION lib)
