# MoDOT - Missouri Department Of Transportation                          ![image](https://user-images.githubusercontent.com/103028610/199921143-1f8c170e-db99-425b-95e3-10031bd2188d.png)


This project requires the automation of carriers registration that operates wholly within the jurisdiction and maintains applicable insurance filings as licenses are   required for the movement of loads that exceed the established oversize and overweight permit limits.

## Table of Contents

 - [Framework Architecture](#framework-architecture)
 - [Description](#description)
 - [Installation](#installation)
 - [How To Use](#how-to-use)
 - [Execution](#execution)
 - [CI/CD](#ci-/-cd)
 - [Reports](#reports)

### Framework Architecture

       MoDOT	 
         |_src/main/java
	     |	|_com.celtic.automation.cmcs.factory
         |		|	|_DriverFactory.java
         |	|_com.celtic.automation.cmcs.pages
         |		|	|_AccountTabPage.java
         |		|	|_BillingTab.java
         |		|	|_CommonObjects.java
	     |		|	|_DashBoardPage.java
	     |		|	|_DistanceTabPage.java
         |		|	|_Enquiry.java
         |		|	|_Financepage.java
	     |		|	|_FleetPage.java
	     |		|	|_FleetTabPage.java
         |		|	|_InstallmentPage.java
         |		|	|_InventoryPage.java
	     |		|	|_LoginPage.java
	     |		|	|_Payment.java
         |		|	|_PaymentTab.java
         |		|	|_SupplementaryDocuments.java
	     |		|	|_VehicleAdd.java
	     |		|	|_VehicleAmend.java
         |		|	|_VehicleDelete.java
         |		|	|_VehicleDocuments.java
	     |		|	|_VehicleTabPage.java
	     |		|	|_WgtGroup.java
         |		|	|_WgtGroupAdd.java
         |	|_com.celtic.automation.cmcs.util
         |			|_ConfigReader.java
         |			|_ElementUtil.java
         |			|_Generic_Functions.java
         |			|_ReadExcelUtil.java
	     |			|_Screenshot_Utility.java
         |			|_WriteExcelUtil.java
         |_src/test/java
         |	|_apphooks
         |	    	|	|_Application_Hooks.java
         |	|_parallel
         |		|	|_Parallel_Run.java
         |		|	|_RWC_001.java
         |	|_testrunner
         |			|_FailedRun.java
         |			|_MyTestRunner.java
         |
         |_src/test/resources  
	     |		|_config
	     |		|_DataProvider
	     |		|_Parallel (placed all the feature files)
	     |		|_cucumber.properties
	     |		|_extent-config.xml
	     |		|log4j.properties
	     |
	     |_JRE System Library
	     |_Maven Dependencies
	     |_TestNG
	     |_src
	     |_test-output
	     |_test-output-thread
	     |_application.log
	     |_Executable.BAT
	     |_pom.xml
		
		
### Description

The cucumber BDD testing framework specifies acceptance tests as written from the view of the Celtic. Using keywords such as Given, When, Then and And, acceptance criteria tests known as feature files can then be broken down into testable steps. Cucumber has a built in report generation whereby Feature files tested are automatically written to cucumbers own reporting system


### Installation

- JDK 1.8 (make sure Java class path is set)
- Maven 
- Eclipse
- Browser driver (make sure you have your desired browser driver and class path is set)

### How To Use

- Get a git clone from [here](https://github.com/Madhumptester/Celtic_final-enhancement) or download zip and set it up in your local workspace.      
- Import your project into Eclipse
- In Eclipse, go to the File menu and select: 
- File -> Import -> Existing Maven Projects into Workspace
- Select the directory containing this file
- Click Finish

### Execution

We can execute the test cases by Maven using following steps

- mvn install
- mvn clean test (defualt will run on local browser)

We can execute the test cases by TestNG runner using following steps

- Redirect to MyTestRunner in Eclipse 
- Click on run as - TestNg runner 

We can execute the test cases by batch file, that stores commands to be executed in a serial order

- File saved with the extension . bat
- Double click on the file to run the .exe program

### CI/CD

Framework is integrated with Jenkins, it is a process of automating the building and packaging of code for deployment to test. 

- Download and Install Jenkins
- Run Jenkins on Localhost 8080
- Jenkins Server Interface
- Build and Run a Job on Jenkins

#### Build and run job on Jenkins

- Navigate to New Item and click  
  ![image](https://user-images.githubusercontent.com/103028610/200263774-add21660-68c1-4e1f-8503-27e6cc0e74ec.png)

- Provide the name to the project 

  ![image](https://user-images.githubusercontent.com/103028610/200265226-6f32c461-a201-40ec-8fba-c4f3c412ddf0.png)

- Select Freestyle project ![image](https://user-images.githubusercontent.com/103028610/200265382-4d159291-38bb-42f2-9ccd-afb8884380cb.png)

- Select Source Code Management as Git and provide Repository URL
 ![image](https://user-images.githubusercontent.com/103028610/200266056-08354d01-aa0e-49ba-8c3a-03fcc1819596.png)

- We only need to enter credentials when the repository is created as private

- Specify the branch 

  ![image](https://user-images.githubusercontent.com/103028610/200268528-80b0d051-1f88-4b85-878c-261c1a4c647d.png)

- Navigate to Build Triggers and select Build periodically to add scheduler to the job by specifying the cron expressions ![image](https://user-images.githubusercontent.com/103028610/200269284-870d3ce0-e48d-4fc1-9235-1fa02439d727.png)

- Navigate to Build and select the Add build step as - Execute windows batch command ![image](https://user-images.githubusercontent.com/103028610/200270404-eb5a7de9-6993-4051-8195-af9bda81a0b1.png)

- Apply and save 
 
  ![image](https://user-images.githubusercontent.com/103028610/200270572-28b3cbdf-3429-41e6-8d7e-3e322386f0f3.png)

### Reports

Once you ran your tests you can generate the various types of reports. This framework `testng-cucumber-java uses several different types of test reporters to communicate pass/failure.
#### Extent Spark Report:
Report will be generated into test-output. Web server with results will start appearing in your default browser. Apache Spark, We are able to perform the data processing and verify it immediately. When combining Apache Spark and Cucumber, we make a compelling combination that maintains the scale of a system and can prove that the data is being handled correctly.
![image](https://user-images.githubusercontent.com/103028610/199913087-f29e653e-3f38-4906-a0e2-f47a1867d404.png)
#### PDF Report:
All supported reports generate HTML output by default. Reports contains screenshots of the test cases as well as the time stamp, which point towards the start time and end time. The report will give you a brief about test case execution as - Pass, Fail and Skip. Graphical representation has beed designed in the report to make it more  comprehensive.
![image](https://user-images.githubusercontent.com/103028610/199907985-28d508df-d9fa-4f5f-b897-fb4ae6b0bb76.png)
