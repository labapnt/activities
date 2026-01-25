# Global Resource Sharing Activity

This activity catalog describes the concept of global resource sharing across multiple topologies and lab-sites. This activity demonstrates how resource abstraction enables efficient resource utilization and prevents resource hoarding by users or teams.

## Topology: GLOBAL RESOURCE SHARING

### Topology Description
**Two Lab Sites (Lab Site 1 and Lab Site 2) sharing resources across network topologies.**

This topology demonstrates global resource sharing capabilities with two lab sites, each containing:

**Lab Site 1:**
- **Arista L2 Switch** (IP: 192.168.168.112) - Primary switching device
- **vSTC-03** (IP: 192.168.168.220) - Spirent Test Center virtual instance
- **VyOS Router** (IP: 192.168.168.126) - Routing device
- **Connections**: Ethernet (ETH) links connecting all nodes

**Lab Site 2:**
- **Arista L2 Switch** (IP: 192.168.168.111) - Primary switching device
- **vSTC-04** (IP: 192.168.168.204) - Spirent Test Center virtual instance
- **VyOS Router** (IP: 192.168.168.105) - Routing device
- **Connections**: Ethernet (ETH) links connecting all nodes

**Resource Sharing:**
- Resources from Lab Site 1 and Lab Site 2 are shared across topologies
- **Resource Abstraction**: Mechanism that enables resource sharing without hoarding
- **Global Sharing**: Resources can be shared across different topologies and lab-sites

### Topology Diagram

![Global Resource Sharing Topology](globalResourceSharing/globalResourceSharing.svg)

### Topology Details
- **Topology1**: Primary topology with DUT1 and DUT2 resources
- **Topology2**: Secondary topology/lab-site sharing resources
- **Resource Abstraction Layer**: Enables transparent resource sharing
- **Global Resource Pool**: Shared pool of resources across topologies
- **Resource Management**: Prevents resource hoarding through abstraction

### Resource Sharing Concept

The global resource sharing concept addresses the challenge of resource hoarding by implementing resource abstraction:

1. **Resource Abstraction**: Resources are abstracted from physical devices
2. **Shared Resource Pool**: Resources are pooled and shared across topologies
3. **Dynamic Allocation**: Resources are allocated dynamically based on demand
4. **Automatic Release**: Resources are automatically released when not in use
5. **Cross-Topology Access**: Resources can be accessed from multiple topologies
6. **Lab-Site Integration**: Resources from different lab-sites can be shared

### Key Benefits

1. **Prevents Resource Hoarding**: 
   - Resources cannot be held indefinitely by a single user or team
   - Automatic release mechanisms ensure availability
   - Resource abstraction prevents exclusive ownership

2. **Improved Resource Utilization**:
   - Resources are shared efficiently across multiple topologies
   - Idle resources are made available to other users
   - Better overall resource utilization

3. **Flexibility**:
   - Resources can be dynamically allocated and released
   - Multiple topologies can access the same resources
   - Lab-sites can share resources seamlessly

4. **Cost Efficiency**:
   - Reduces need for duplicate resources
   - Maximizes return on investment for expensive equipment
   - Enables better resource planning



### Benefits of Global Resource Sharing

1. **Prevents Hoarding**: Resources cannot be held indefinitely
2. **Improved Utilization**: Better resource utilization across topologies
3. **Cost Efficiency**: Reduces need for duplicate resources
4. **Flexibility**: Dynamic resource allocation and release
5. **Scalability**: Scales resource availability across lab-sites
6. **Efficiency**: Optimizes resource usage and reduces waste
7. **Collaboration**: Enables resource sharing between teams
8. **Abstraction**: Simplifies resource management through abstraction

### Lab-Site Integration

#### Cross-Lab-Site Resource Sharing
- **Network Connectivity**: Secure network connections between lab-sites
- **Resource Discovery**: Automatic discovery of shared resources
- **Access Control**: Secure access control across lab boundaries
- **Synchronization**: Resource state synchronization
- **Monitoring**: Cross-lab-site resource monitoring
