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