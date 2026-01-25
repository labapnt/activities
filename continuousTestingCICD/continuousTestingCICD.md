# Continuous Testing (CI/CD) Pipeline Activity

This activity catalog describes the integration of network testing into continuous integration and continuous deployment (CI/CD) pipelines. This activity demonstrates how Velocity and iTest integrate with CI/CD runners to enable automated network testing as part of software development workflows.

## Topology: CONTINUOUS TESTING (CI/CD) PIPELINE

### Topology Description
**STC Port A → NetScout L1 → DUT (Any) → NetScout L1 → STC Port B**

**CI/CD Integration**: A CI runner (GitLab/Jenkins/etc.) and Velocity + iTest integration system

This topology demonstrates continuous testing capabilities where:
- **Spirent Test Center (STC) Port A**: Source of automated traffic generation
- **NetScout L1**: Layer 1 monitoring/analysis device (first instance)
- **DUT (Any)**: Device Under Test - any network device (switch, router, firewall, etc.)
- **NetScout L1**: Layer 1 monitoring/analysis device (second instance)
- **Spirent Test Center (STC) Port B**: Traffic destination/receiver
- **CI/CD Runner**: GitLab CI, Jenkins, GitHub Actions, or other CI/CD platform
- **Velocity + iTest Integration**: Automated test orchestration and execution system

### Topology Diagram

![Continuous Testing CI CD Pipeline Topology](continuousTestingCICD/continuousTestingCICD.svg)

### Topology Details
- **Traffic Source**: STC Port A (automated)
- **Traffic Destination**: STC Port B (automated)
- **DUT**: Any network device (switch, router, firewall, load balancer, etc.)
- **Monitoring**: NetScout L1 devices for traffic analysis
- **CI/CD Platform**: GitLab CI, Jenkins, GitHub Actions, Azure DevOps, or similar
- **Integration**: Velocity platform with iTest integration
- **Test Focus**: Automated network testing in CI/CD pipelines, software/integration testing

### CI/CD Pipeline Integration Overview

The continuous testing pipeline integrates network testing into software development workflows:

1. **Code Commit/Trigger**: Developer commits code or creates merge request
2. **CI/CD Runner Activation**: CI/CD platform (GitLab/Jenkins/etc.) triggers pipeline
3. **Velocity + iTest Integration**: 
   - Velocity orchestrates test environment provisioning
   - iTest executes automated test cases
   - Test results are collected and analyzed
4. **Network Test Execution**:
   - STC generates traffic automatically
   - NetScout L1 monitors and captures traffic
   - DUT processes traffic
   - Results are collected
5. **Result Integration**: Test results are integrated back into CI/CD pipeline
6. **Pipeline Decision**: Pass/fail decision based on test results
7. **Reporting**: Test reports generated and attached to CI/CD pipeline

### Velocity + iTest Integration

#### Integration Components
- **Velocity CLI**: Command-line interface for Velocity platform
- **iTest Framework**: Automated test execution framework
- **API Integration**: RESTful API for programmatic access
- **Result Collectors**: Automated test result collection and parsing
- **Notification Systems**: Integration with Slack, email, webhooks

#### Integration Features
- **Automated Topology Management**: Reserve, configure, and release topologies programmatically
- **Test Execution Automation**: Execute test suites without manual intervention
- **Result Collection**: Automatically collect and parse test results
- **Artifact Management**: Store and retrieve test artifacts
- **Notification Integration**: Send test results to various notification channels
- **Baseline Comparison**: Compare test results against baseline metrics

### Benefits of CI/CD Integration

1. **Early Detection**: Catch network issues early in development cycle
2. **Automated Testing**: Eliminate manual test execution
3. **Consistent Testing**: Ensure consistent test execution across environments
4. **Faster Feedback**: Provide rapid feedback to developers
5. **Regression Prevention**: Prevent regressions from being merged
6. **Documentation**: Automatically document test execution and results
7. **Scalability**: Scale testing across multiple branches and developers
8. **Integration**: Seamlessly integrate with existing development workflows

### Software/Integration Focus

This activity focuses on **software and integration work**, not hardware:

- **CI/CD Platform Integration**: Integrating with GitLab, Jenkins, GitHub Actions, etc.
- **API Integration**: Using Velocity and iTest APIs for automation
- **Pipeline Configuration**: Writing and maintaining CI/CD pipeline configurations
- **Test Automation**: Automating test execution and result collection
- **Integration Testing**: Testing software integrations and configurations
- **DevOps Practices**: Implementing DevOps practices for network testing

By following these steps, you can integrate network testing into your CI/CD pipelines, enabling continuous testing of network devices and configurations as part of your software development workflow.

