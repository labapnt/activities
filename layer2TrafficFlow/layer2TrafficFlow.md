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

### Test Cases

1. **Basic Layer 2 Traffic Flow Test**: 
   - Configure basic VLAN on DUT switch
   - Generate traffic from STC Port A to STC Port B
   - Verify traffic flow through the DUT switch
   - Monitor traffic using NetScout L1 devices

2. **VLAN Trunk Configuration Test**:
   - Configure VLAN trunk ports on DUT switch
   - Generate tagged traffic from STC Port A
   - Verify VLAN tagging/untagging through the switch
   - Validate traffic reception on STC Port B

3. **VLAN Access Port Configuration Test**:
   - Configure VLAN access ports on DUT switch
   - Generate untagged traffic from STC Port A
   - Verify VLAN assignment on access ports
   - Validate traffic flow to STC Port B

4. **Mixed Trunk/Access Port Configuration Test**:
   - Configure a mix of trunk and access ports on DUT switch
   - Generate traffic with various VLAN configurations
   - Verify proper VLAN handling across different port types
   - Validate end-to-end traffic flow

5. **Multiple VLAN Traffic Flow Test**:
   - Configure multiple VLANs on DUT switch
   - Generate traffic for different VLANs from STC Port A
   - Verify VLAN isolation and proper forwarding
   - Validate traffic reception per VLAN on STC Port B
