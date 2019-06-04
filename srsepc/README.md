## Limitation Implementations

The following changes were made to implement LTE-M eMTC

1. Eliminating the MBMS channel from srsepc/src/CMakeLists.txt
It was chosen to delete the path from the CMakeLists to not be included in any build file the code wrote for MBMS.
Eliminating the 24th line from the file mentioned above.
add_subdirectory(mbms-gw)
// add_subdirectory(mbms-gw)



For these changes in algorithm, the following sources were followed:
[1] https://www.sharetechnote.com/html/Handbook_LTE_BL_CE_MPDCCH.html
[2] https://www.sharetechnote.com/html/Handbook_LTE_BL_CE.html
