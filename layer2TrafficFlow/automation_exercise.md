### Exercise Instructions

1. **Finding and Reserving the Topology**:
   1. Navigate to the `Topologies` tab in the navigation bar
   2. Search for "Layer 2 Traffic Flow" topology
   3. Click on `View Details` to review topology specifications
   4. Click on `Reserve` to reserve the topology
   5. Set reservation duration (recommended: 60 minutes for comprehensive testing)
   6. Click `Confirm Reservation` to finalize

2. **Starting the Topology**:
   1. Navigate to the `Reservations` tab
   2. Select your Layer 2 Traffic Flow reservation
   3. Click on `Start Topology` to activate the topology
   4. Wait for all devices (STC, NetScout L1, DUT Switch) to be ready

3. **Configuring the DUT Switch**:
   1. Access the DUT switch console through the topology interface
   2. Configure VLANs as required for your test case:
      - For Arista: Use `vlan` commands
      - For Cisco: Use `vlan database` or `vlan` commands
   3. Configure port types:
      - **Trunk ports**: Configure to carry multiple VLANs (tagged)
      - **Access ports**: Configure to assign a single VLAN (untagged)
   4. Apply VLAN configurations to appropriate interfaces
   5. Verify configuration using `show vlan` or equivalent commands

4. **Selecting and Running a Test Case**:
   1. Navigate to the `Test Cases` tab
   2. Search for Layer 2 Traffic Flow test cases
   3. Select the appropriate test case based on your testing requirements:
      - Basic Layer 2 Traffic Flow Test
      - VLAN Trunk Configuration Test
      - VLAN Access Port Configuration Test
      - Mixed Trunk/Access Port Configuration Test
      - Multiple VLAN Traffic Flow Test
   4. Click on `View Details` to review test case requirements
   5. Click on `Select` to choose the test case

5. **Configuring Traffic Generation**:
   1. Access STC Port A configuration
   2. Configure traffic parameters:
      - Source MAC address
      - Destination MAC address
      - VLAN tags (if testing trunk ports)
      - Frame size and rate
      - Traffic duration
   3. Configure STC Port B to receive and analyze traffic
   4. Set up NetScout L1 devices for traffic monitoring

6. **Executing the Test**:
   1. On the topology details page, find the `Run Test Case` section
   2. Select your chosen test case from the dropdown
   3. Review test parameters and adjust if needed
   4. Click on `Start Test` to begin execution
   5. Monitor test progress through the topology console

7. **Viewing Test Results**:
   1. Navigate to the `Test Results` tab on the topology details page
   2. Review the following metrics:
      - Traffic sent/received statistics
      - Frame loss (if any)
      - Latency measurements
      - VLAN tag preservation/removal
      - Port statistics from DUT switch
      - NetScout L1 analysis results
   3. Analyze any errors or warnings
   4. Compare results against expected behavior

8. **Generating Test Report**:
   1. From the `Test Results` tab, click on `Generate Report`
   2. Customize report to include:
      - VLAN configuration details
      - Traffic flow statistics
      - Port type configurations (trunk/access)
      - Performance metrics
      - Error analysis
   3. Export report in your preferred format (PDF, Excel, HTML)
   4. Review and share with your team

### Configuration Examples

#### Arista Switch VLAN Configuration
```
configure terminal
vlan 10
   name VLAN_10
vlan 20
   name VLAN_20
interface Ethernet1
   switchport mode trunk
   switchport trunk allowed vlan 10,20
interface Ethernet2
   switchport mode access
   switchport access vlan 10
```

#### Cisco Switch VLAN Configuration
```
configure terminal
vlan 10
   name VLAN_10
vlan 20
   name VLAN_20
interface GigabitEthernet0/1
   switchport mode trunk
   switchport trunk allowed vlan 10,20
interface GigabitEthernet0/2
   switchport mode access
   switchport access vlan 10
```

### Best Practices

1. **VLAN Planning**: Plan your VLAN configuration before starting the test
2. **Port Configuration**: Ensure port types (trunk/access) match your test requirements
3. **Traffic Patterns**: Use realistic traffic patterns and frame sizes
4. **Monitoring**: Utilize NetScout L1 devices to capture detailed traffic analysis
5. **Documentation**: Document VLAN configurations and test parameters for reproducibility
6. **Verification**: Always verify DUT switch configuration before running traffic tests
7. **Baseline**: Establish baseline performance metrics before testing different configurations

### Troubleshooting

- **No Traffic Received**: Verify VLAN configuration on DUT switch and port assignments
- **VLAN Tag Issues**: Check trunk port configuration and allowed VLANs
- **Access Port Problems**: Verify access VLAN assignment matches traffic VLAN
- **High Frame Loss**: Check port speeds, duplex settings, and switch capacity
- **NetScout L1 Not Capturing**: Verify NetScout L1 device configuration and port mirroring/SPAN settings

By following these steps, you can effectively test Layer 2 traffic flow, VLAN configurations, and validate switch behavior with various trunk and access port mixes.