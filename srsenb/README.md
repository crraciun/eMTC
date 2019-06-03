## Limitation Implementations

The following changes were made to implement LTE-M eMTC

1. From srsenb/src/phy/phch_worker.cc was eliminated the ability of the eNB to set a certain CFI. In LTE-M, CFI=3. The line 434 was deleted
//srslte_enb_dl_set_cfi(&enb_dl, dl_grants[t_tx_dl].cfi);
