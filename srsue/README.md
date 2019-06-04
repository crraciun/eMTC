## Limitation Implementations

The following changes were made to implement LTE-M eMTC

1. Adding in srsue/src/phy/phch_recv.cc the following line (38)

const uint32_t cfi=3;

2. Adding in srsue/src/phy/phch_worker.cc the following line (38)

const uint32_t cfi=3;



For these changes in algorithm, the following sources were followed: &nbsp;
[1] https://www.sharetechnote.com/html/Handbook_LTE_BL_CE_MPDCCH.html &nbsp;
[2] https://www.sharetechnote.com/html/Handbook_LTE_BL_CE.html
