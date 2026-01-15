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

![Continuous Testing CI/CD Pipeline Topology](continuousTestingCICD/continuousTestingCICD.svg)

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

### Test Cases

1. **CI/CD Pipeline Integration Test**:
   - Trigger test from CI/CD runner
   - Verify Velocity + iTest integration
   - Validate test environment provisioning
   - Confirm test execution automation

2. **Automated Network Regression Test**:
   - Execute network tests on code changes
   - Verify DUT behavior with new software/firmware
   - Validate network functionality
   - Compare results against baseline

3. **Continuous Performance Testing**:
   - Execute performance tests in CI/CD pipeline
   - Monitor network performance metrics
   - Validate performance thresholds
   - Generate performance reports

4. **Multi-Device Testing Pipeline**:
   - Test multiple DUT types in parallel
   - Execute device-specific test suites
   - Aggregate results across devices
   - Generate consolidated reports

5. **Integration Test Suite Execution**:
   - Run comprehensive integration test suite
   - Validate end-to-end network functionality
   - Test interoperability between components
   - Verify configuration compatibility

### Exercise Instructions

1. **Setting Up CI/CD Integration**:
   1. Configure CI/CD runner (GitLab/Jenkins/etc.) to integrate with Velocity
   2. Install and configure Velocity + iTest integration components
   3. Set up authentication and API access
   4. Configure pipeline YAML files or Jenkinsfiles
   5. Define test triggers and conditions

2. **Configuring Pipeline Test Stages**:
   1. Create test stage in CI/CD pipeline configuration:
      ```yaml
      # Example GitLab CI configuration
      network_test:
        stage: test
        script:
          - velocity-cli reserve-topology --name "CI/CD Test Topology"
          - velocity-cli configure-dut --template "baseline-config"
          - itest run --test-suite "regression-tests"
          - velocity-cli collect-results --output "test-results.xml"
      ```
   2. Configure test environment variables
   3. Set up test result artifacts collection
   4. Define pass/fail criteria

3. **Triggering Automated Tests**:
   1. Commit code changes or create merge request
   2. CI/CD runner automatically triggers pipeline
   3. Observe pipeline execution in CI/CD platform
   4. Monitor Velocity + iTest integration logs
   5. Track test execution progress

4. **Monitoring Test Execution**:
   1. Access Velocity platform to monitor test execution
   2. Observe automatic resource allocation:
      - STC ports are allocated
      - NetScout L1 devices are configured
      - DUT is provisioned and configured
   3. Monitor test execution in real-time
   4. Review test logs and progress

5. **Viewing Test Results in CI/CD Pipeline**:
   1. Navigate to CI/CD pipeline execution page
   2. Review test stage output and logs
   3. Access test result artifacts:
      - Test reports (XML, JSON, HTML)
      - Performance metrics
      - Traffic analysis data
      - DUT configuration snapshots
   4. Review pass/fail status
   5. Analyze any test failures

6. **Integrating Results into Pipeline**:
   1. Configure result parsing in CI/CD pipeline
   2. Set up test result publishing:
      - JUnit XML reports
      - Test coverage reports
      - Performance benchmarks
   3. Configure notifications for test failures
   4. Set up test result dashboards
   5. Integrate with issue tracking systems

7. **Pipeline Decision and Actions**:
   1. Review pipeline pass/fail decision
   2. For passing tests:
      - Pipeline continues to next stages
      - Code can be merged/deployed
      - Test results are archived
   3. For failing tests:
      - Pipeline stops or alerts
      - Test failure details are reported
      - Developer is notified
      - Test artifacts are preserved for analysis

8. **Generating Test Reports**:
   1. Access test reports from CI/CD artifacts
   2. Review automated test reports:
      - Test execution summary
      - Performance metrics
      - Network traffic analysis
      - DUT configuration details
      - Comparison with baseline results
   3. Export reports for documentation
   4. Share reports with development team

### CI/CD Integration Examples

#### GitLab CI Configuration
```yaml
stages:
  - build
  - test
  - deploy

variables:
  VELOCITY_API_URL: "https://velocity.example.com/api"
  VELOCITY_API_TOKEN: "${VELOCITY_API_TOKEN}"
  ITEST_VERSION: "latest"

network_test:
  stage: test
  image: velocity/itest-runner:latest
  script:
    - echo "Starting network test execution"
    - velocity-cli login --url $VELOCITY_API_URL --token $VELOCITY_API_TOKEN
    - velocity-cli reserve-topology --name "cicd-test-topology" --duration 30
    - velocity-cli wait-for-topology --status ready
    - velocity-cli configure-dut --template "baseline" --device "dut-01"
    - itest run --suite "regression" --output "test-results.xml"
    - velocity-cli collect-results --format junit --output "junit-results.xml"
    - velocity-cli release-topology
  artifacts:
    reports:
      junit: junit-results.xml
    paths:
      - test-results.xml
      - velocity-logs/
    expire_in: 1 week
  only:
    - merge_requests
    - main
    - develop
```

#### Jenkins Pipeline Configuration
```groovy
pipeline {
    agent any
    
    environment {
        VELOCITY_API_URL = 'https://velocity.example.com/api'
        VELOCITY_API_TOKEN = credentials('velocity-api-token')
    }
    
    stages {
        stage('Network Test') {
            steps {
                script {
                    sh '''
                        velocity-cli login --url ${VELOCITY_API_URL} --token ${VELOCITY_API_TOKEN}
                        velocity-cli reserve-topology --name "jenkins-test-topology"
                        velocity-cli configure-dut --template "baseline"
                        itest run --suite "regression" --output "test-results.xml"
                        velocity-cli collect-results --format junit
                        velocity-cli release-topology
                    '''
                }
            }
            post {
                always {
                    junit 'test-results.xml'
                    archiveArtifacts artifacts: 'test-results.xml', fingerprint: true
                }
            }
        }
    }
}
```

#### GitHub Actions Configuration
```yaml
name: Network Testing Pipeline

on:
  push:
    branches: [ main, develop ]
  pull_request:
    branches: [ main ]

jobs:
  network-test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      
      - name: Setup Velocity CLI
        uses: velocity/setup-cli@v1
        with:
          api-url: ${{ secrets.VELOCITY_API_URL }}
          api-token: ${{ secrets.VELOCITY_API_TOKEN }}
      
      - name: Reserve Test Topology
        run: velocity-cli reserve-topology --name "github-test-topology"
      
      - name: Configure DUT
        run: velocity-cli configure-dut --template "baseline"
      
      - name: Run Network Tests
        run: itest run --suite "regression" --output "test-results.xml"
      
      - name: Collect Test Results
        run: velocity-cli collect-results --format junit
      
      - name: Upload Test Results
        uses: actions/upload-artifact@v2
        with:
          name: test-results
          path: test-results.xml
      
      - name: Release Topology
        if: always()
        run: velocity-cli release-topology
```

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

### Best Practices

1. **Pipeline Configuration**: 
   - Use version-controlled pipeline configurations
   - Implement proper secret management
   - Set appropriate timeout values
   - Configure retry logic for transient failures

2. **Test Environment Management**:
   - Reserve topologies early in pipeline
   - Implement topology cleanup in finally blocks
   - Use topology templates for consistency
   - Monitor topology availability

3. **Test Execution**:
   - Run fast tests first (smoke tests)
   - Execute comprehensive tests on main branches
   - Use parallel test execution when possible
   - Implement test result caching

4. **Result Management**:
   - Standardize result formats (JUnit XML, etc.)
   - Archive test artifacts for debugging
   - Implement result comparison and trending
   - Set up test result dashboards

5. **Error Handling**:
   - Implement proper error handling and cleanup
   - Always release topologies in finally blocks
   - Log detailed error information
   - Notify on test failures

6. **Performance Optimization**:
   - Minimize topology reservation time
   - Use test result caching
   - Implement parallel test execution
   - Optimize test suite selection

7. **Security**:
   - Use secure credential management
   - Implement API token rotation
   - Restrict API access permissions
   - Audit pipeline executions

### Troubleshooting

- **CI/CD Integration Failures**: Verify API credentials and connectivity
- **Topology Reservation Issues**: Check topology availability and resource limits
- **Test Execution Failures**: Review test logs and DUT configuration
- **Result Collection Problems**: Verify result format and parsing logic
- **Pipeline Timeouts**: Increase timeout values or optimize test execution
- **Authentication Errors**: Verify API tokens and permissions
- **Resource Conflicts**: Implement proper resource locking and cleanup

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

