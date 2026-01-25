# Layer 2 Traffic Flow Activity

This activity catalog describes the detailed steps for testing Layer 2 traffic flow through a network topology with VLAN configuration on a DUT (Device Under Test) switch.

## Topology: LAYER 2 TRAFFIC FLOW

### Topology Description
**STC Port A → NetScout L1 → DUT Switch (Arista or Cisco) → NetScout L1 → STC Port B**

This topology is designed to test Layer 2 traffic flow and VLAN functionality through a network switch. The setup includes:
- **Spirent Test Center (STC) Port A**: Source of traffic generation
- **NetScout L1**: Layer 1 monitoring/analysis device (first instance)
- **DUT Switch**: Device Under Test - either Arista or Cisco switch
- **NetScout L1**: Layer 1 monitoring/analysis device (second instance)
- **Spirent Test Center (STC) Port B**: Traffic destination/receiver

### Topology Diagram

![Layer 2 Traffic Flow Topology](layer2TrafficFlow/layer2TrafficFlow.svg)

### Topology Details
- **Traffic Source**: STC Port A
- **Traffic Destination**: STC Port B
- **DUT Switch**: Arista or Cisco switch with VLAN configuration capability
- **Monitoring**: NetScout L1 devices for traffic analysis
- **Test Focus**: Layer 2 traffic flow, VLAN configuration, trunk/access port mixes
