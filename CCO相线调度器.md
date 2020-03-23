---
title:CSMA调度器
tags: CCO,相线,软件
grammar_cjkRuby: true
---

# MAC_CsmaMain
## CCO
### sof 
scheduler = MAC_CsGetScheduler(PLC_PHASE_ALL);
返回 g_mac_csma_ca_scheduler.all_phase_scheduler;
### ncf
scheduler = MAC_CsGetScheduler(PLC_PHASE_ALL);
返回  g_mac_csma_ca_scheduler.all_phase_scheduler;
### sack
scheduler = g_mac_csma_ca_scheduler.slot_config.curr_scheduler;
### mpdu_status_update_req/sack_timeout/unexpected_mpdu
scheduler = g_mac_csma_ca_scheduler.slot_config.curr_scheduler;