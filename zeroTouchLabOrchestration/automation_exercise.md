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