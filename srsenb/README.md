## Limitation Implementations

The following changes were made to implement LTE-M eMTC

1. From srsenb/src/phy/phch_worker.cc was eliminated the ability of the eNB to set a certain CFI. In LTE-M, CFI=3. The line 434 was deleted
//srslte_enb_dl_set_cfi(&enb_dl, dl_grants[t_tx_dl].cfi);

2. From srsenb/src/mac/mac.cc 
The line 650 was deleted
 //dl_sched_res->cfi = sched_result.cfi;

3. From srsenb/src/mac/mac.cc
The following line was added
dl_sched_res->cfi=3;
