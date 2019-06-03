## Limitation Implementations

The following changes were made to implement LTE-M eMTC

1. Adding in srsue/src/phy/phch_recv.cc the following line (38)

const uint32_t cfi=3;

2. Adding in srsue/src/phy/phch_worker.cc the following line (38)

const uint32_t cfi=3;
