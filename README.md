# Wiiisdom Ops for Tableau (formerly Kinesis-CI) - Sample Project

Education and innovation is a sample project for users of the Wiiisdom Ops for Tableau tool for Tableau.
Wiiisdom Ops for Tableau is a test framework that adds automated testing and continuous integration capability to Tableau Server.
For more information on Wiiisdom Ops for Tableau, please visit http://wiiisdom.com

![screenshot](/screenshot.png)

## Concept

This project is designed to give you an example for setting up your testing projects in Wiiisdom Ops for Tableau.

It contains a collection of test cases for a Tableau Workbook – Education and Innovation,
including the following test cases:

#### Functional Testing
-	Load data into a database
-	Publish Tableau workbooks and data sources to Tableau Server
-	Refresh data extracts
-	Filters
-	Parameters
-	Checking data against an expected data set
-	Checking the layout of the Dashboard to an expected layout
-	Checking data against pre-defined rules and criterias
-	Checking data against the datasource by an SQL query in the underlying database
-	Running custom webdriver commands (required for SSO and custom login pages)
-	Switch Tab
-   Selecting Marks for testing interactivity/ user clicks

#### Regression Testing
-   Running regression test on a Tableau dashboard to compare against a baseline in terms of data, layout, filter and parameter consitency

#### Cross Environment Testing
-   Comparing the same Tableau View on two different environments i.e. dev and prod or two different Tableau Server versions, when doing and upgrade, in terms of data, layout, filter and parameter consitency

#### Performance Testing
-   Testing the performance of your Tableau Server by driving load against it


This example goes hand in hand with the documentation of Wiiisdom Ops for Tableau, which you can find under https://wiiisdom.com/documents


## Directory layout

File Type    | Description
------------ | --------------
``src`` | Contains the Tableau source files that have been imported into the given Project
``context`` | Contains the JSON files that define your context variables. For more information on context variables refer to the documentation under  https://wiiisdom.com/documents/#/command-line-interface
``test`` | Contains files related to the individual Tests that have been created within the Project
``test/<TEST_NAME>/resources`` | Test resources. These are typically data files (.csv) needed to load data into source systems (i.e. databases) or validate data to expected results
``test/<TEST_NAME>/kinesis.json`` | JSON files that describe the individual Test steps that have been created within the Project
``project.json`` | JSON file that contains the key information to identify the individual Projects. This is only needed for Kinesis Designer, but not to run tests from the Command Line Interface

For more information on the Directory Layout please see https://wiiisdom.com/documents/#/getting-started?id=create-new-project

## Integration with CI tools

If you want to run tests automatically on a Continuous Integration Server, for example on Jenkins, TeamCity or any other similar tool, then you will need to install the Kinesis Command Line Interface to the server where your CI/CD server is running.

Command Line Interface allows you to run previously created Kinesis tests and integrate it with the CI tool of your choice.

For more information on the integration of Wiiisdom Ops for Tableau and Jenkins, please see https://wiiisdom.com/documents/#/continuous-integration
<<<<<<< HEAD


=======

