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

![Zero-Touch Lab Orchestration Topology](zeroTouchLabOrchestration.svg)

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

### Exercise Instructions

For detailed step-by-step exercise instructions, see [Automation Exercise Guide](automation_exercise.md).
