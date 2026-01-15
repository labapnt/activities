# Zero-Touch Lab Orchestration Activity

This activity catalog describes the automated orchestration workflow for zero-touch lab setup and test execution. This activity demonstrates how Velocity automates the entire lab provisioning and testing process with minimal user intervention.

## Topology: ZERO-TOUCH LAB ORCHESTRATION

### Topology Description
**"User selects topology" → Velocity allocates ports → NetScout L1 auto-patches → DUT gets configured → STC runs a test**

This topology demonstrates a fully automated lab orchestration workflow where:
1. **User selects topology**: User chooses a topology from the catalog
2. **Velocity allocates ports**: Velocity platform automatically allocates and reserves required ports
3. **NetScout L1 auto-patches**: NetScout L1 devices automatically configure and patch connections
4. **DUT gets configured**: Device Under Test (DUT) is automatically configured with required settings
5. **STC runs a test**: Spirent Test Center automatically executes the test case

### Topology Diagram

![Zero-Touch Lab Orchestration Topology](zeroTouchLabOrchestration/zeroTouchLabOrchestration.svg)

### Topology Details
- **Orchestration Platform**: Velocity
- **Test Equipment**: Spirent Test Center (STC)
- **Monitoring Equipment**: NetScout L1
- **Device Under Test**: DUT (switch, router, or other network device)
- **Automation Level**: Fully automated zero-touch provisioning and testing

### Workflow Overview

The zero-touch orchestration workflow eliminates manual configuration steps and provides an end-to-end automated testing experience:

1. **Topology Selection**: User selects a topology from the catalog
2. **Resource Allocation**: Velocity automatically:
   - Allocates STC ports
   - Reserves NetScout L1 devices
   - Provisions DUT access
   - Configures network connectivity
3. **Auto-Patching**: NetScout L1 devices automatically:
   - Establish physical/logical connections
   - Configure port mirroring/SPAN
   - Set up traffic monitoring
4. **DUT Configuration**: Velocity automatically:
   - Connects to DUT management interface
   - Applies configuration templates
   - Validates configuration
   - Verifies device readiness
5. **Test Execution**: STC automatically:
   - Loads test case parameters
   - Configures traffic profiles
   - Executes test scenarios
   - Collects results

### Test Cases

1. **Automated Topology Provisioning Test**:
   - Select a topology from catalog
   - Verify automatic port allocation
   - Validate resource reservation
   - Confirm connectivity establishment

2. **Auto-Patching Validation Test**:
   - Verify NetScout L1 auto-patching
   - Validate port mirroring configuration
   - Confirm traffic visibility
   - Test monitoring capabilities

3. **Automated DUT Configuration Test**:
   - Verify automatic DUT connection
   - Validate configuration template application
   - Confirm configuration verification
   - Test rollback capabilities

4. **End-to-End Automated Test Execution**:
   - Execute complete zero-touch workflow
   - Verify all automation steps
   - Validate test results collection
   - Confirm automated reporting

5. **Multi-Topology Orchestration Test**:
   - Select multiple topologies
   - Verify parallel resource allocation
   - Validate concurrent test execution
   - Confirm resource isolation

### Exercise Instructions

1. **Selecting a Topology**:
   1. Navigate to the `Topologies` tab in the navigation bar
   2. Browse or search for available topologies
   3. Review topology details and requirements
   4. Click on `Select Topology` to initiate zero-touch orchestration
   5. The system will automatically begin the orchestration process

2. **Monitoring Automatic Resource Allocation**:
   1. After topology selection, observe the automatic resource allocation process:
      - Velocity allocates STC ports automatically
      - NetScout L1 devices are reserved and configured
      - DUT access is provisioned
      - Network paths are established
   2. Monitor the orchestration dashboard for progress updates
   3. Review allocated resources in the `Resources` tab
   4. Verify all required components are available

3. **Observing NetScout L1 Auto-Patching**:
   1. Navigate to the topology console to observe auto-patching
   2. Verify NetScout L1 devices automatically:
      - Establish connections to DUT ports
      - Configure port mirroring/SPAN sessions
      - Set up traffic monitoring
      - Enable packet capture
   3. Review NetScout L1 configuration in the device console
   4. Confirm traffic visibility is established

4. **Monitoring Automated DUT Configuration**:
   1. Access the DUT management interface through the topology console
   2. Observe automatic configuration process:
      - Velocity connects to DUT
      - Configuration template is applied
      - Settings are validated
      - Device status is verified
   3. Review applied configuration using `show running-config` or equivalent
   4. Verify DUT is ready for testing

5. **Selecting and Executing a Test Case**:
   1. Navigate to the `Test Cases` tab
   2. Select a test case compatible with your topology
   3. Click on `View Details` to review test requirements
   4. Click on `Select` to choose the test case
   5. The system will automatically:
      - Configure STC with test parameters
      - Set up traffic profiles
      - Prepare monitoring tools
      - Initialize test execution

6. **Monitoring Automated Test Execution**:
   1. Navigate to the topology details page
   2. Find the `Test Execution` section
   3. Observe automatic test execution:
      - STC generates traffic
      - NetScout L1 captures and analyzes traffic
      - DUT processes traffic
      - Results are collected automatically
   4. Monitor real-time test progress and metrics
   5. Review any automated alerts or notifications

7. **Viewing Automated Test Results**:
   1. Navigate to the `Test Results` tab on the topology details page
   2. Review automatically collected results:
      - Traffic statistics
      - Performance metrics
      - Error analysis
      - NetScout L1 capture data
      - DUT performance data
   3. Analyze automated test reports
   4. Review any automated recommendations

8. **Generating Automated Test Report**:
   1. From the `Test Results` tab, click on `Generate Report`
   2. The system automatically includes:
      - Topology configuration details
      - Resource allocation information
      - DUT configuration applied
      - Test execution parameters
      - Complete test results
      - Performance analysis
   3. Export report in your preferred format (PDF, Excel, HTML)
   4. Review and share automated report

### Automation Features

#### Velocity Orchestration Capabilities
- **Intelligent Resource Allocation**: Automatically selects optimal resources based on topology requirements
- **Template-Based Configuration**: Uses configuration templates for consistent DUT setup
- **Health Monitoring**: Continuously monitors device and connection health
- **Error Recovery**: Automatically handles and recovers from common errors
- **Rollback Capability**: Can automatically rollback configurations if needed

#### NetScout L1 Auto-Patching Features
- **Automatic Port Discovery**: Discovers and maps available ports
- **Intelligent Patching**: Automatically establishes optimal connections
- **Port Mirroring Configuration**: Configures SPAN/mirroring sessions automatically
- **Traffic Visibility**: Ensures complete traffic visibility without manual configuration
- **Monitoring Setup**: Automatically configures monitoring and capture settings

#### DUT Auto-Configuration Features
- **Template Management**: Uses pre-defined configuration templates
- **Validation**: Automatically validates applied configurations
- **Compatibility Checking**: Verifies DUT compatibility with topology requirements
- **State Management**: Tracks and manages DUT state throughout testing
- **Configuration Backup**: Automatically backs up original configuration

#### STC Automated Testing Features
- **Test Case Integration**: Automatically loads test case parameters
- **Traffic Profile Configuration**: Configures traffic based on test requirements
- **Result Collection**: Automatically collects and stores test results
- **Performance Analysis**: Provides automated performance analysis
- **Report Generation**: Generates comprehensive test reports automatically

### Configuration Templates

#### DUT Configuration Template Example
```
# Velocity Auto-Configuration Template
# Applied automatically during orchestration

# Basic Interface Configuration
interface GigabitEthernet0/1
   description Auto-configured by Velocity
   no shutdown
   speed 1000
   duplex full

interface GigabitEthernet0/2
   description Auto-configured by Velocity
   no shutdown
   speed 1000
   duplex full

# VLAN Configuration (if required)
vlan 10
   name Test_VLAN_10

# Routing Configuration (if required)
# ip route 0.0.0.0 0.0.0.0 [gateway]

# Verification Commands
# show interfaces status
# show vlan brief
```

### Best Practices

1. **Topology Selection**: Choose topologies that match your testing requirements
2. **Resource Planning**: Review resource availability before selecting complex topologies
3. **Template Customization**: Customize DUT configuration templates for your specific needs
4. **Monitoring**: Monitor orchestration progress to identify any issues early
5. **Validation**: Always validate automated configurations before critical tests
6. **Documentation**: Document any custom templates or configurations
7. **Testing**: Test automation workflows in non-production environments first
8. **Backup**: Ensure original configurations are backed up before automated changes

### Troubleshooting

- **Resource Allocation Failures**: Check resource availability and reservation conflicts
- **Auto-Patching Issues**: Verify NetScout L1 device connectivity and configuration
- **DUT Configuration Errors**: Review configuration templates and DUT compatibility
- **Test Execution Failures**: Check STC connectivity and test case parameters
- **Orchestration Timeouts**: Review topology complexity and increase timeout values if needed
- **Connection Issues**: Verify network paths and device accessibility
- **Template Application Failures**: Validate template syntax and DUT command compatibility

### Benefits of Zero-Touch Orchestration

1. **Time Savings**: Eliminates manual configuration steps, reducing setup time by up to 90%
2. **Consistency**: Ensures consistent configurations across multiple test runs
3. **Error Reduction**: Minimizes human errors in configuration and setup
4. **Scalability**: Enables parallel execution of multiple topologies and tests
5. **Reproducibility**: Provides repeatable test environments and configurations
6. **Efficiency**: Optimizes resource utilization and allocation
7. **Visibility**: Provides comprehensive monitoring and logging of all automation steps

By following these steps, you can leverage the zero-touch lab orchestration capabilities to streamline your testing workflows, reduce manual effort, and increase testing efficiency and reliability.

