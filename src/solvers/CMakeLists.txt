if(SOLVER STREQUAL "hlle")
  set(SOLVER_HEADER "HLLEFun.hpp")
  target_compile_definitions(swe_noRes PRIVATE SOLVER=0)
  target_compile_definitions(swe_hardRes_wTaskSharing PRIVATE SOLVER=0)
  target_compile_definitions(swe_softRes_hashes PRIVATE SOLVER=0)
  target_compile_definitions(swe_softRes_hardRes_hashes PRIVATE SOLVER=0)
  #  target_compile_definitions(swe_softRes_admiss_useShared_v1 PRIVATE SOLVER=0)
  #  target_compile_definitions(swe_softRes_admiss_useShared_v2 PRIVATE SOLVER=0)
  #  target_compile_definitions(swe_softRes_admiss_useShared_v2_NONBLOCKING PRIVATE SOLVER=0)
  target_compile_definitions(swe_softRes_admiss_useShared PRIVATE SOLVER=0)
  target_compile_definitions(swe_softRes_admiss_redundant PRIVATE SOLVER=0)
  target_compile_definitions(swe_checkpointRestart PRIVATE SOLVER=0)
  # target_compile_definitions(swe_tests PRIVATE SOLVER=0)
elseif(SOLVER STREQUAL "fwave")
  set(SOLVER_HEADER "FWave.hpp")
  target_compile_definitions(swe_noRes PRIVATE SOLVER=1)
  target_compile_definitions(swe_hardRes_wTaskSharing PRIVATE SOLVER=1)
  target_compile_definitions(swe_softRes_hashes PRIVATE SOLVER=1)
  target_compile_definitions(swe_softRes_hardRes_hashes PRIVATE SOLVER=1)
  #  target_compile_definitions(swe_softRes_admiss_useShared_v1 PRIVATE SOLVER=1)
  #  target_compile_definitions(swe_softRes_admiss_useShared_v2 PRIVATE SOLVER=1)
  #  target_compile_definitions(swe_softRes_admiss_useShared_v2_NONBLOCKING PRIVATE SOLVER=1)
  target_compile_definitions(swe_softRes_admiss_useShared PRIVATE SOLVER=1)
  target_compile_definitions(swe_softRes_admiss_redundant PRIVATE SOLVER=1)
  target_compile_definitions(swe_checkpointRestart PRIVATE SOLVER=1)
  # target_compile_definitions(swe_tests PRIVATE SOLVER=1)

  target_sources(swe_noRes PRIVATE WavePropagation.hpp)
  target_sources(swe_hardRes_wTaskSharing PRIVATE WavePropagation.hpp)
  target_sources(swe_softRes_hashes PRIVATE WavePropagation.hpp)
  target_sources(swe_softRes_hardRes_hashes PRIVATE WavePropagation.hpp)
  #target_sources(swe_softRes_admiss_useShared_v1 PRIVATE WavePropagation.hpp)
  #target_sources(swe_softRes_admiss_useShared_v2 PRIVATE WavePropagation.hpp)
  #target_sources(swe_softRes_admiss_useShared_v2_NONBLOCKING PRIVATE WavePropagation.hpp)
  target_sources(swe_softRes_admiss_useShared PRIVATE WavePropagation.hpp)
  target_sources(swe_softRes_admiss_redundant PRIVATE WavePropagation.hpp)
  target_sources(swe_checkpointRestart PRIVATE WavePropagation.hpp)
  # target_sources(swe_tests PRIVATE WavePropagation.hpp)
elseif(SOLVER STREQUAL "augrie")
  set(SOLVER_HEADER "AugRie.hpp")
  target_compile_definitions(swe_noRes PRIVATE SOLVER=2)
  target_compile_definitions(swe_hardRes_wTaskSharing PRIVATE SOLVER=2)
  target_compile_definitions(swe_softRes_hashes PRIVATE SOLVER=2)
  target_compile_definitions(swe_softRes_hardRes_hashes PRIVATE SOLVER=2)
  #  target_compile_definitions(swe_softRes_admiss_useShared_v2 PRIVATE SOLVER=1)
  #  target_compile_definitions(swe_softRes_admiss_useShared_v2 PRIVATE SOLVER=2)
  #  target_compile_definitions(swe_softRes_admiss_useShared_v2_NONBLOCKING PRIVATE SOLVER=2)
  target_compile_definitions(swe_softRes_admiss_useShared PRIVATE SOLVER=2)
  target_compile_definitions(swe_softRes_admiss_redundant PRIVATE SOLVER=2)
  target_compile_definitions(swe_checkpointRestart PRIVATE SOLVER=2)
  # target_compile_definitions(swe_tests PRIVATE SOLVER=2)

  target_sources(swe_noRes PRIVATE WavePropagation.hpp)
  target_sources(swe_hardRes_wTaskSharing PRIVATE WavePropagation.hpp)
  target_sources(swe_softRes_hashes PRIVATE WavePropagation.hpp)
  target_sources(swe_softRes_hardRes_hashes PRIVATE WavePropagation.hpp)
  #target_sources(swe_softRes_admiss_useShared_v1 PRIVATE WavePropagation.hpp)
  #target_sources(swe_softRes_admiss_useShared_v2 PRIVATE WavePropagation.hpp)
  #target_sources(swe_softRes_admiss_useShared_v2_NONBLOCKING PRIVATE WavePropagation.hpp)
  target_sources(swe_softRes_admiss_useShared PRIVATE WavePropagation.hpp)
  target_sources(swe_softRes_admiss_redundant PRIVATE WavePropagation.hpp)
  target_sources(swe_checkpointRestart PRIVATE WavePropagation.hpp)
  # target_sources(swe_tests PRIVATE WavePropagation.hpp)
else()
message(FATAL_ERROR "SOLVER must be one of: ${SOLVERS}")
endif()

message(STATUS "Using Riemann solver: ${SOLVER}")

target_sources(swe_noRes PRIVATE ${SOLVER_HEADER})
target_sources(swe_hardRes_wTaskSharing PRIVATE ${SOLVER_HEADER})
target_sources(swe_softRes_hashes PRIVATE ${SOLVER_HEADER})
target_sources(swe_softRes_hardRes_hashes PRIVATE ${SOLVER_HEADER})
#target_sources(swe_softRes_admiss_useShared_v1 PRIVATE ${SOLVER_HEADER})
#target_sources(swe_softRes_admiss_useShared_v2 PRIVATE ${SOLVER_HEADER})
#target_sources(swe_softRes_admiss_useShared_v2_NONBLOCKING PRIVATE ${SOLVER_HEADER})
target_sources(swe_softRes_admiss_useShared PRIVATE ${SOLVER_HEADER})
target_sources(swe_softRes_admiss_redundant PRIVATE ${SOLVER_HEADER})
target_sources(swe_checkpointRestart PRIVATE ${SOLVER_HEADER})
# target_sources(swe_tests PRIVATE ${SOLVER_HEADER})
