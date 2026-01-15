# User Workflow
This activity catalog describes the detailed steps of finding resources and Topologies, placing reservation, conducting a test, and viewing the results. 
This activity catalog is intended for users who are new to the system. 


### **Finding and Reserving Resources and Topologies**
1. **Navigate to the Topology Catalog**:
   1. Click on the `Topologies` tab in the navigation bar. This will take you to the Topology Catalog page. Here, you can view a list of available topologies that you can reserve for testing. You can filter the topologies based on various criteria such as the number of nodes, the type of nodes, and the software stack installed on the nodes. You can also search for specific topologies using the search bar.
   2. Click on the `View Details` button to view more information about a topology. This will take you to the Topology Details page. Here, you can view the topology's description, the number of nodes, the type of nodes, and the software stack installed on the nodes. You can also view the topology's diagram and the list of reserved and available nodes.
   3. Click on the `Reserve` button to reserve the topology. This will take you to the Reservation page. Here, you can select the start and end dates for the reservation and provide additional information such as the purpose of the reservation.
   4. Click on the `Confirm Reservation` button to confirm the reservation. This will reserve the topology for the specified duration. You can view the reservation details on the Reservation page.
   5. Click on the `Start Topology` button to start the reserved topology. This will take you to the Topology Console page. Here, you can access the nodes in the topology and interact with them using the console.
   6. Click on the `Stop Topology` button to stop the reserved topology. This will stop the topology and release the nodes. You can view the reservation details on the Reservation page.
2. **Navigate to the Resource Catalog**:
   1. Click on the `Resources` tab in the navigation bar. This will take you to the Resource Catalog page. Here, you can view a list of available resources that you can reserve for testing. You can filter the resources based on various criteria such as the type of resource, the location of the resource, and the software stack installed on the resource. You can also search for specific resources using the search bar.
   2. Click on the `View Details` button to view more information about a resource. This will take you to the Resource Details page. Here, you can view the resource's description, the type of resource, the location of the resource, and the software stack installed on the resource. You can also view the resource's diagram and the list of reserved and available nodes.
   3. Click on the `Reserve` button to reserve the resource. This will take you to the Reservation page. Here, you can select the start and end dates for the reservation and provide additional information such as the purpose of the reservation.
   4. Click on the `Confirm Reservation` button to confirm the reservation. This will reserve the resource for the specified duration. You can view the reservation details on the Reservation page.
   5. Click on the `Start Resource` button to start the reserved resource. This will take you to the Resource Console page. Here, you can access the resource and interact with it using the console.  
   6. Click on the `Stop Resource` button to stop the reserved resource. This will stop the resource and release it. You can view the reservation details on the Reservation page.
3. **Manage Reservations**
   1. Click on the `Reservations` tab in the navigation bar. This will take you to the Reservations page. Here, you can view a list of your reservations and their status. You can filter the reservations based on various criteria such as the start and end dates, the type of reservation, and the status of the reservation. You can also search for specific reservations using the search bar.
   2. Click on the `View Details` button to view more information about a reservation. This will take you to the Reservation Details page. Here, you can view the reservation's details such as the start and end dates, the purpose of the reservation, and the status of the reservation. You can also view the reservation's topology or resource and the list of reserved nodes.
   3. Click on the `Start` button to start the reserved topology or resource. This will take you to the Topology Console or Resource Console page. Here, you can access the nodes in the topology or resource and interact with them using the console.
   4. Click on the `Stop` button to stop the reserved topology or resource. This will stop the topology or resource and release the nodes. You can view the reservation details on the Reservation page.
   5. Click on the `Delete` button to delete the reservation. This will cancel the reservation and release the nodes. You can view the reservation details on the Reservation page.
   6. Click on the `Extend` button to extend the reservation. This will allow you to select a new end date for the reservation. You can view the reservation details on the Reservation page.
   7. Click on the `Clone` button to clone the reservation. This will create a new reservation with the same details as the original reservation. You can view the reservation details on the Reservation page.

### **Finding and Running Test Cases on a Reserved Topology**

After reserving a topology, you can search for available test cases to run. 
This section guides you through finding and running the test cases for your reserved topology.

1. ** Navigate to the Test Cases Catalog**
   1. Click on the `Test Cases` tab in the navigation bar to access the Test Cases Catalog page. Here, you can view a list of available test cases.
   2. Use the filter options and search bar to find specific test cases relevant to your topology.

2. **Selecting a Test Case**
   1. Click on the `View Details` button next to a test case to learn more about it, including its purpose and requirements.
   2. Select the test case you wish to run by clicking on the `Select` button.

3. **Running a Test Case on a Reserved Topology**
   1. Navigate to your reserved topology by clicking on the `Reservations` tab and selecting your topology.
   2. On the topology's details page, find the `Run Test Case` section.
   3. From the dropdown menu, select the test case you previously chose.
   4. Click on the `Start Test` button to initiate the test case execution on the reserved topology.

### **Viewing Test Results**
1. Once the test case has finished running, navigate to the `Test Results` tab on the topology's details page.
2. Here, you can view the outcome of the test case, including any metrics or logs generated during the execution.

By following these steps, you can effectively utilize your reserved topology to run test cases and ensure your setup meets the required specifications and performance criteria.

### **Generating a Test Report**
After the test case execution is complete, generating a comprehensive test report is crucial for documentation and analysis purposes. 
Follow these steps to generate a test report for your test case execution on a reserved or new reservation topology.

1. **Access Test Results**: Navigate to the `Test Results` tab on the topology's details page where your test case was executed.

2. **Analyze Test Outcomes**: Review the test execution outcomes, including metrics, logs, and any errors or warnings generated during the test. This step is vital for understanding the performance and behavior of the topology under test.

3. **Generate Report**: Look for a `Generate Report` button or link on the `Test Results` page. Clicking this button will initiate the process of compiling the test results into a structured report.

4. **Customize Report (Optional)**: If available, select options to customize the report to include specific data points, charts, or sections relevant to your analysis needs. This might include filtering options for time ranges, specific metrics, or error types.

5. **Download/Export Report**: Once the report is generated, you will have the option to download or export the report in various formats (e.g., PDF, Excel, HTML). Choose the format that best suits your documentation or presentation needs.

6. **Review and Share**: Review the downloaded or exported report to ensure it meets your requirements. Share the report with your team, stakeholders, or include it in your project documentation for future reference.

By generating a test report, you can document the performance and configuration validation of your topology, providing a valuable resource for troubleshooting, optimization, and compliance verification.

### **Running Test Cases on a New Reservation**

For users who need to run test cases without an existing reservation, this section outlines the process of creating a new reservation specifically for a test case execution. 
This approach is useful for testing specific configurations or performance scenarios on demand.

1. **Finding and Selecting a Test Case**
   1. Navigate to the `Test Cases` tab in the main navigation bar to access the catalog of available test cases.
   2. Utilize the search bar and filter options to locate a test case that matches your testing requirements.
   3. Click on the `View Details` button next to your chosen test case to see more information, including its purpose, requirements, and any prerequisites.
   4. Select the test case for execution by clicking on the `Select` button.

2. **Choosing a Topology for the Test Case**
   1. After selecting a test case, you will be prompted to choose a topology on which to run the test case.
   2. Browse through the list of available topologies, using filters if necessary to find one that suits the requirements of the test case.
   3. Select your desired topology by clicking on it. This will take you to a configuration page for the new reservation.

3. **Configuring the Reservation**
   1. On the reservation configuration page, you can optionally set various parameters for the test case and the topology, such as:
      - Start and end times for the reservation.
      - Specific configuration settings required by the test case or preferred for the topology.
   2. Review your configuration settings to ensure they meet the test case and topology requirements.

3. **Placing the New Reservation**
   1. Once you have configured the reservation to your satisfaction, click on the `Place Reservation` button to finalize the process.
   2. You will receive a confirmation of your reservation, along with details on how to access the reserved topology and start the test case execution.

4. **Starting the Test Case Execution**
   1. Navigate to the `Reservations` tab and select your new reservation from the list.
   2. On the reservation's details page, find the `Run Test Case` section.
   3. Click on the `Start Test` button to begin the execution of the test case on the newly reserved topology.

5. **Viewing Test Results**
   1. Test execution results can be accessed from the `Test Results` tab on the reservation's details page once the test case has completed.
   2. Review the results, including any metrics or logs generated, to assess the performance and configuration of the topology against the test case requirements.



## Description of Exercises
```To ensure a comprehensive understanding and practical application of the processes outlined above, we will conduct a series of exercises covering all the key areas mentioned. These exercises will include:```

1. **Finding and Selecting a Test Case**: Participants will practice navigating the `Test Cases` tab, using search and filter options to locate specific test cases, and selecting a test case for execution.

2. **Choosing a Topology for the Test Case**: Exercise tasks will guide participants through the process of choosing an appropriate topology for their selected test case, emphasizing the importance of matching test case requirements with topology capabilities.

3. **Configuring the Reservation**: Participants will learn how to configure a reservation by setting parameters such as start and end times, and adjusting specific configuration settings required by the test case or preferred for the topology.

4. **Placing the New Reservation**: This exercise will walk participants through the process of finalizing their reservation, from clicking the `Place Reservation` button to receiving confirmation of the reservation.

5. **Starting the Test Case Execution**: Participants will execute the selected test case on their newly reserved topology, starting from navigating to the `Reservations` tab to clicking the `Start Test` button.

6. **Viewing Test Results**: Finally, participants will access and review the test execution results, learning how to assess the performance and configuration of the topology against the test case requirements.

```The following exercise is designed to provide hands-on experience with the platform, enhancing the ability to efficiently utilize the system for testing and validation purposes.```


### **Loopback Traffic Test Topology**
The Loopback Traffic Test Topology is designed to test network connectivity and traffic flow within a single device. This topology is useful for troubleshooting and verifying the functionality of network interfaces and protocols.

### Topology Diagram

![Looback Topology](customActivity/test.jpeg)


### Topology Details
Device: Spirent Test Center virtual machine
Interface: Port1, Port2
IP Address: 192.168.168.201/24
Gateway: 192.168.168.1

### Test Cases
1. **Bi-directional Traffic Test**: Send traffic from Port1 to Port2 and vice versa to test loopback connectivity. Verify that the traffic is received correctly and without errors.

### Exercise Instructions
1. **Selecting the Test Case**: Choose the `Bi-directional Traffic Test` from the Test Cases Catalog.
2. **Choosing the Topology**: Select the `Loopback Traffic Test Topology` for the test case execution.
3. **Configuring the Reservation**: Set the reservation parameters and configuration settings as needed for the ``Bi-directional Traffic Test`.
4. **Placing the New Reservation**: Finalize the reservation by clicking the `Place Reservation` button.
5. **Starting the Test Case Execution**: Initiate the `Bi-directional Traffic Test` on the reserved topology by clicking the `Start Test` button.
6. **Viewing Test Results**: Access the `Test Results` tab to review the outcome of the `Bi-directional Traffic` execution.
7. **Repeat the Process**: Practice running additional test cases on the same topology to gain familiarity with the testing workflow.
8. **Generate Test Report**: Generate a test report for the executed test cases and review the results for documentation and analysis purposes.

```You can take a quick look at the `Loopback Traffic Test` Topology by clicking the link below or reserving the topology for further learning.```


