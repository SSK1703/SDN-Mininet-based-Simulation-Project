# SDN Learning Switch Control - Orange Problem

## Problem Statement
Implementation of a dynamic learning switch that learns MAC addresses and installs 
OpenFlow rules to minimize flooding and improve network efficiency.

## Setup Instructions
1. Clone POX: `git clone https://github.com/noxrepo/pox`
2. Place `learning_switch.py` in `pox/ext/`
3. Run Controller: `python3 pox.py forwarding.l2_learning`
4. Run Mininet: `sudo mn --topo single,3 --mac --controller remote`

## Test Scenarios
### Scenario 1: Normal Traffic (Learning)
- **Action:** Host 1 pings Host 2.
- **Observation:** Controller learns MACs; subsequent packets follow flow rules.

### Scenario 2: Flow Table Validation
- **Action:** Execute `dpctl dump-flows`.
- **Observation:** Verified that specific rules exist for H1 and H2.

## Performance Analysis
- **Latency:** Average ping time was [X] ms.
- **Throughput:** iPerf measured [X] Gbits/sec.
