if (BLD_EXAMPLE)
  add_subdirectory (example)
endif (BLD_EXAMPLE)

if (BLD_AFFYIO)
  add_subdirectory (affyio)
endif (BLD_AFFYIO)

if (BLD_STADEN)
  add_subdirectory (staden_io_lib)
endif (BLD_STADEN)
