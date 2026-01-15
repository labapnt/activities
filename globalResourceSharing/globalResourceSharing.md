# Global Resource Sharing Activity

This activity catalog describes the concept of global resource sharing across multiple topologies and lab-sites. This activity demonstrates how resource abstraction enables efficient resource utilization and prevents resource hoarding by users or teams.

## Topology: GLOBAL RESOURCE SHARING

### Topology Description
**TOPOLOGY1 has resources DUT1 and DUT2 that are shared with resources from another "LAB-SITE", TOPOLOGY2.**

This topology demonstrates global resource sharing capabilities where:
- **Topology1**: Contains resources DUT1 and DUT2
- **Topology2**: Another lab-site that shares resources with Topology1
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

### Test Cases

1. **Resource Sharing Validation Test**:
   - Verify DUT1 and DUT2 can be shared between Topology1 and Topology2
   - Validate resource abstraction layer functionality
   - Confirm resources are accessible from both topologies
   - Test concurrent access scenarios

2. **Resource Allocation Test**:
   - Test dynamic resource allocation from shared pool
   - Verify fair resource distribution
   - Validate priority-based allocation
   - Test resource reservation mechanisms

3. **Resource Release Test**:
   - Verify automatic resource release when not in use
   - Test resource release on topology completion
   - Validate resource cleanup processes
   - Confirm resources return to shared pool

4. **Cross-Lab-Site Sharing Test**:
   - Test resource sharing between different lab-sites
   - Verify network connectivity for shared resources
   - Validate resource access across lab boundaries
   - Test resource synchronization

5. **Resource Hoarding Prevention Test**:
   - Verify resources cannot be held indefinitely
   - Test automatic timeout mechanisms
   - Validate resource release policies
   - Confirm fair resource access

6. **Concurrent Topology Test**:
   - Test multiple topologies accessing shared resources
   - Verify resource isolation and security
   - Validate performance with shared resources
   - Test conflict resolution

### Exercise Instructions

1. **Understanding Resource Abstraction**:
   1. Navigate to the `Resources` tab in the navigation bar
   2. Review resource abstraction concepts in documentation
   3. Understand how resources are abstracted from physical devices
   4. Learn about resource sharing mechanisms
   5. Review resource allocation policies

2. **Creating Topology1 with Shared Resources**:
   1. Navigate to the `Topologies` tab
   2. Create or select Topology1
   3. Add resources DUT1 and DUT2 to Topology1
   4. Configure DUT1 and DUT2 as shared resources:
      - Enable resource sharing flag
      - Set sharing policies
      - Configure access permissions
   5. Reserve Topology1 with shared resources

3. **Creating Topology2 from Different Lab-Site**:
   1. Navigate to the `Topologies` tab
   2. Create or select Topology2 (from different lab-site)
   3. Configure Topology2 to access shared resources
   4. Request access to DUT1 and DUT2 from Topology1
   5. Verify resource availability and connectivity

4. **Verifying Resource Sharing**:
   1. Access Topology1 console
   2. Verify DUT1 and DUT2 are available and configured
   3. Access Topology2 console
   4. Verify DUT1 and DUT2 are accessible from Topology2
   5. Confirm both topologies can use the shared resources

5. **Testing Resource Abstraction**:
   1. Review resource abstraction layer in Velocity platform
   2. Verify resources are abstracted from physical devices
   3. Test resource allocation from shared pool
   4. Validate resource metadata and properties
   5. Confirm resource abstraction enables sharing

6. **Testing Resource Release**:
   1. Complete testing on Topology1
   2. Release Topology1 resources
   3. Verify resources are returned to shared pool
   4. Confirm Topology2 can still access resources
   5. Test automatic resource release mechanisms

7. **Monitoring Resource Utilization**:
   1. Navigate to the `Resources` tab
   2. View global resource pool status
   3. Monitor resource allocation across topologies
   4. Review resource utilization metrics
   5. Analyze resource sharing efficiency

8. **Testing Resource Hoarding Prevention**:
   1. Attempt to hold resources indefinitely
   2. Verify automatic timeout mechanisms
   3. Test resource release policies
   4. Confirm resources cannot be hoarded
   5. Validate fair resource access

9. **Running Tests on Shared Resources**:
   1. Select a test case compatible with shared resources
   2. Execute test on Topology1 using DUT1 and DUT2
   3. Execute test on Topology2 using same DUT1 and DUT2
   4. Verify test isolation and security
   5. Review test results from both topologies

10. **Viewing Resource Sharing Reports**:
    1. Navigate to the `Reports` tab
    2. Generate resource utilization report
    3. Review resource sharing statistics
    4. Analyze resource allocation patterns
    5. Identify optimization opportunities

### Resource Abstraction Architecture

#### Abstraction Layer Components
- **Resource Virtualization**: Physical resources are virtualized
- **Resource Pool Management**: Centralized pool of shared resources
- **Access Control**: Secure access control for shared resources
- **Resource Metadata**: Metadata management for abstracted resources
- **Allocation Engine**: Intelligent resource allocation engine

#### Resource Sharing Mechanisms
- **Time-Based Sharing**: Resources shared based on time slots
- **Priority-Based Allocation**: Resources allocated based on priority
- **Demand-Based Distribution**: Resources distributed based on demand
- **Automatic Release**: Resources automatically released when idle
- **Conflict Resolution**: Mechanisms to resolve resource conflicts

### Configuration Examples

#### Enabling Resource Sharing in Topology1
```yaml
# Topology1 Configuration
topology:
  name: "Topology1"
  resources:
    - name: "DUT1"
      type: "switch"
      sharing:
        enabled: true
        policy: "time-based"
        max_duration: "4 hours"
        auto_release: true
    - name: "DUT2"
      type: "router"
      sharing:
        enabled: true
        policy: "demand-based"
        max_duration: "4 hours"
        auto_release: true
```

#### Accessing Shared Resources in Topology2
```yaml
# Topology2 Configuration
topology:
  name: "Topology2"
  lab_site: "Lab-Site-B"
  shared_resources:
    - source_topology: "Topology1"
      resources:
        - "DUT1"
        - "DUT2"
  access_policy:
    priority: "normal"
    timeout: "2 hours"
```

#### Resource Abstraction API Example
```python
# Example: Accessing shared resources via API
from velocity_api import VelocityClient

client = VelocityClient()

# Get shared resources from Topology1
shared_resources = client.get_shared_resources(
    source_topology="Topology1",
    resources=["DUT1", "DUT2"]
)

# Allocate shared resources for Topology2
allocation = client.allocate_shared_resources(
    topology="Topology2",
    resources=shared_resources,
    duration="2 hours"
)

# Use shared resources
for resource in allocation.resources:
    print(f"Using shared resource: {resource.name}")
    # Perform operations on shared resource

# Release resources (automatic on completion)
client.release_resources(allocation.id)
```

### Best Practices

1. **Resource Planning**:
   - Identify resources suitable for sharing
   - Plan resource allocation policies
   - Define sharing time limits
   - Establish priority rules

2. **Sharing Configuration**:
   - Enable sharing only for appropriate resources
   - Configure reasonable time limits
   - Set up automatic release mechanisms
   - Define access permissions

3. **Resource Management**:
   - Monitor resource utilization
   - Review sharing statistics regularly
   - Optimize resource allocation
   - Balance resource availability

4. **Security and Isolation**:
   - Ensure proper access control
   - Maintain resource isolation
   - Implement security policies
   - Monitor resource access

5. **Documentation**:
   - Document shared resources
   - Maintain resource inventory
   - Track sharing agreements
   - Document access policies

6. **Monitoring**:
   - Monitor resource utilization
   - Track sharing efficiency
   - Identify bottlenecks
   - Optimize resource distribution

7. **Communication**:
   - Coordinate resource usage
   - Communicate sharing schedules
   - Notify users of resource availability
   - Share resource status updates

### Troubleshooting

- **Resource Not Available**: Check resource sharing configuration and availability
- **Access Denied**: Verify access permissions and sharing policies
- **Resource Conflicts**: Review resource allocation and resolve conflicts
- **Connection Issues**: Verify network connectivity between lab-sites
- **Resource Release Failures**: Check automatic release mechanisms and policies
- **Performance Issues**: Review resource utilization and sharing overhead
- **Synchronization Problems**: Verify resource synchronization across lab-sites

### Resource Hoarding Prevention Mechanisms

1. **Time Limits**:
   - Maximum reservation duration
   - Automatic timeout mechanisms
   - Idle timeout policies
   - Grace period for extensions

2. **Usage Monitoring**:
   - Track resource usage patterns
   - Monitor idle resources
   - Identify hoarding behavior
   - Generate alerts for violations

3. **Automatic Release**:
   - Release on topology completion
   - Release on inactivity
   - Release on timeout
   - Release on policy violation

4. **Fair Allocation**:
   - Round-robin allocation
   - Priority-based allocation
   - Demand-based distribution
   - Equal access policies

5. **Resource Abstraction Benefits**:
   - Prevents exclusive ownership
   - Enables transparent sharing
   - Simplifies resource management
   - Provides flexibility

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

#### Lab-Site Configuration
```yaml
# Lab-Site Configuration
lab_sites:
  - name: "Lab-Site-A"
    location: "Data Center A"
    resources:
      - "DUT1"
      - "DUT2"
    sharing:
      enabled: true
      accessible_by: ["Lab-Site-B"]
  
  - name: "Lab-Site-B"
    location: "Data Center B"
    shared_resources:
      - source: "Lab-Site-A"
        resources: ["DUT1", "DUT2"]
```

By following these steps, you can implement global resource sharing, prevent resource hoarding through resource abstraction, and enable efficient resource utilization across multiple topologies and lab-sites.

