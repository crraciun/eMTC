## Limitation Implementations

The following changes were made to implement LTE-M eMTC

1. From srsenb/src/phy/phch_worker.cc was eliminated the ability of the eNB to set a certain CFI. In LTE-M, CFI=3. The line 434 was deleted
//srslte_enb_dl_set_cfi(&enb_dl, dl_grants[t_tx_dl].cfi);

The line 454 was deleted
  //encode_phich(ul_grants[t_tx_ul].phich, ul_grants[t_tx_ul].nof_phich);
The lines 840 to 857 were deleted


2. From srsenb/src/mac/mac.cc 
The line 650 was deleted
 //dl_sched_res->cfi = sched_result.cfi;

3. From srsenb/src/mac/mac.cc
The following line was added
dl_sched_res->cfi=3;



For these changes in algorithm, the following sources were followed:
[1] https://www.sharetechnote.com/html/Handbook_LTE_BL_CE_MPDCCH.html
[2] https://www.sharetechnote.com/html/Handbook_LTE_BL_CE.html
