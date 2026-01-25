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

### Benefits of Topology Abstraction and Resource Abstraction Layer

The **Resource Abstraction Layer** is a key component that enables Topology Abstraction, providing significant benefits for resource management and reservation handling:

#### 1. **Flexible Resource Resolution for Recurring Reservations**
- **At Start Time Resolution**: Resources are allocated only when each reservation instance is scheduled to start, allowing for dynamic resource availability
- **At Create Time Resolution**: All resources for recurring reservation instances are resolved at creation time, ensuring resource availability for the entire series
- **Automatic Maintenance**: Velocity periodically (every 12 hours) checks and generates new future resolved reservation events, maintaining up to 300 instances over 12 months

#### 2. **Prevents Resource Hoarding**
- **Abstract Topologies**: By abstracting resources from physical devices, the Resource Abstraction Layer prevents users from holding resources indefinitely
- **Dynamic Allocation**: Resources are allocated based on actual need and availability, not permanent ownership
- **Automatic Release**: Resources are automatically released when reservation instances complete, making them available for other users

#### 3. **Improved Resource Availability and Conflict Management**
- **Conflict Detection**: When resources cannot be resolved due to conflicts, Velocity provides clear notifications about which instances could not be created
- **Resource Guarantees**: For recurring reservations with 300+ instances, Velocity provides warnings and options to adjust schedules to ensure resource availability
- **Proactive Management**: The system proactively manages resource availability across all reservation instances

#### 4. **Enhanced Scalability and Efficiency**
- **Cross-Topology Sharing**: The Resource Abstraction Layer enables resources from Lab Site 1 and Lab Site 2 to be shared seamlessly across different topologies
- **Global Resource Pool**: All abstracted resources are available in a global pool, maximizing utilization
- **Reduced Duplication**: Eliminates the need for duplicate resources across different topologies or lab-sites

#### 5. **Simplified Reservation Management**
- **Edit Capabilities**: Allows editing of active, scheduled, or cancellation of individual instances within recurring reservations
- **Transparent Resource Access**: Users can access resources without needing to know the physical location or specific device details
- **Unified Management**: Single interface for managing resources across multiple lab-sites and topologies

#### 6. **Cost Optimization**
- **Better Resource Utilization**: Resources are used more efficiently across all topologies and lab-sites
- **Reduced Idle Time**: Resources are automatically made available when not in use, reducing idle periods
- **Investment Maximization**: Expensive equipment is shared and utilized more effectively across the organization

The Resource Abstraction Layer acts as the intelligent intermediary that manages resource allocation, prevents hoarding, and ensures optimal utilization of network testing resources across the entire Velocity platform.

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
