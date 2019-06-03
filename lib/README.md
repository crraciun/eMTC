## Limitation Implementations

The following changes were made to implement LTE-M eMTC

1. From lib/src/phy/enb/enb_dl.c were eliminated the following channels:
PCFICH, PHICH. For completing this task, the following codes were erased:

a. Line 82 to 90 for disabling the PCFICH initialization
/*   if (srslte_pcfich_init(&q->pcfich, 0)) {
      fprintf(stderr, "Error creating PCFICH object\n");
      goto clean_exit;
    }
    if (srslte_phich_init(&q->phich, 0)) {
      fprintf(stderr, "Error creating PHICH object\n");
      goto clean_exit;
    }
 */
 b. Line 141
 //    srslte_pcfich_free(&q->pcfich);
 c. Line 197 to 205 for disabling any cell set-up with PCFICH and PHICH
 /*      if (srslte_pcfich_set_cell(&q->pcfich, &q->regs, q->cell)) {
        fprintf(stderr, "Error creating PCFICH object\n");
        return SRSLTE_ERROR;
      }
      if (srslte_phich_set_cell(&q->phich, &q->regs, q->cell)) {
        fprintf(stderr, "Error creating PHICH object\n");
        return SRSLTE_ERROR;
      }
*/
d. Line 359 to 372
e. Line 380 was deleted
// srslte_enb_dl_put_pcfich(q, sf_idx);
f. Line 387 was deleted
//  srslte_enb_dl_put_pcfich(q, sf_idx1);

2. From lib/examples/pdsch_enodeb.c was eliminated the following channel:
PCFICH. For completing this task, the following codes were erased:

a. Line 95
//srslte_pcfich_t pcfich;
b. From line 359 to 368
c. Line 875
 //     srslte_pcfich_encode(&pcfich, cfi, sf_symbols, sf_idx);

3. From lib/src/phy/ue/ue_dl.c were deleted 
a. Lines 110 to 122
b. Line 170 and 171
//    srslte_pcfich_free(&q->pcfich);
//    srslte_phich_free(&q->phich);
c. Lines 233 to 241
d. Lines 421 to 435
e. Lines 965 to 970

3. The following line was added in lib/src/phy/ue/ue_dl.c at line 54
const uint32_t cfi=3;

4. Static was removed from the following functions:
Line 768 static int dci_blind_search(..)
Line 856 static int find_dl_dci_type_siprarnti(..)
Line 876 static int find_dl_dci_type_crnti(..)
