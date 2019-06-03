## Limitation Implementations

The following changes were made to implement LTE-M eMTC

1. Eliminating the MBMS channel from srsepc/src/CMakeLists.txt
It was chosen to delete the path from the CMakeLists to not be included in any build file the code wrote for MBMS.
add_subdirectory(mbms-gw)
// add_subdirectory(mbms-gw)
