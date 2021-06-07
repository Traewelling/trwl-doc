
- [1. Introduction](#1-introduction)
  * [1.1 Purpose](#11-purpose)
  * [1.2 Scope](#12-scope)
  * [1.3 Intended Audience](#13-intended-audience)
  * [1.4 Document Terminology and Acronyms](#14-document-terminology-and-acronyms)
  * [1.5  References](#15--references)
  * [1.6 Document Structure](#16-document-structure)
- [2. Evaluation Mission and Test Motivation](#2-evaluation-mission-and-test-motivation)
  * [2.1 Background](#21-background)
  * [2.2 Evaluation Mission](#22-evaluation-mission)
  * [2.3 Test Motivators](#23-test-motivators)
- [3. Target Test Items](#3-target-test-items)
- [4. Outline of Planned Tests](#4-outline-of-planned-tests)
  * [4.1 Outline of Test Inclusions](#41-outline-of-test-inclusions)
  * [4.2 Outline of Other Candidates for Potential Inclusion](#42-outline-of-other-candidates-for-potential-inclusion)
  * [4.3 Outline of Test Exclusions](#43-outline-of-test-exclusions)
- [5. Test Approach](#5-test-approach)
  * [5.1 Initial Test-Idea Catalogs and Other Reference Sources](#51-initial-test-idea-catalogs-and-other-reference-sources)
  * [5.2 Testing Techniques and Types](#52-testing-techniques-and-types)
    + [5.2.1 Data and Database Integrity Testing](#521-data-and-database-integrity-testing)
    + [5.2.2 Functional Testing](#522-functional-testing)
    + [5.2.3 Business Cycle Testing](#523-business-cycle-testing)
    + [5.2.4 User Interface Testing](#524-user-interface-testing)
    + [5.2.5 Performance Profiling](#525-performance-profiling)
    + [5.2.6 Load Testing](#526-load-testing)
    + [5.2.7 Stress Testing](#527-stress-testing)
    + [5.2.8 Volume Testing](#528-volume-testing)
    + [5.2.9 Security and Access Control Testing](#529-security-and-access-control-testing)
    + [5.2.10 Failover and Recovery Testing](#5210-failover-and-recovery-testing)
    + [5.2.11 Configuration Testing](#5211-configuration-testing)
    + [5.2.12 Installation Testing](#5212-installation-testing)
- [6. Entry and Exit Criteria](#6-entry-and-exit-criteria)
  * [6.1 Test Plan](#61-test-plan)
    + [6.1.1 Test Plan Entry Criteria](#611-test-plan-entry-criteria)
    + [6.1.2 Test Plan Exit Criteria](#612-test-plan-exit-criteria)
    + [6.1.3 Suspension and Resumption Criteria](#613-suspension-and-resumption-criteria)
  * [6.2 Test Cycles](#62-test-cycles)
      - [6.2.1 Test Cycle Entry Criteria](#621-test-cycle-entry-criteria)
      - [6.2.2 Test Cycle Exit Criteria](#622-test-cycle-exit-criteria)
      - [6.2.3 Test Cycle Abnormal Termination](#623-test-cycle-abnormal-termination)
- [7. Deliverables](#7-deliverables)
- [7.1 Test Evaluation Summaries](#71-test-evaluation-summaries)
- [7.2 Reporting on Test Coverage](#72-reporting-on-test-coverage)
- [7.3 Perceived Quality Reports](#73-perceived-quality-reports)
- [7.4 Incident Logs and Change Requests](#74-incident-logs-and-change-requests)
- [7.5 Smoke Test Suite and Supporting Test Scripts](#75-smoke-test-suite-and-supporting-test-scripts)
- [7.6      Additional Work Products](#76------additional-work-products)
  * [7.6.1     Detailed Test Results](#761-----detailed-test-results)
  * [7.6.2     Additional Automated Functional Test Scripts](#762-----additional-automated-functional-test-scripts)
  * [7.6.3     Test Guidelines](#763-----test-guidelines)
  * [7.6.4     Traceability Matrices](#764-----traceability-matrices)
- [8. Testing Workflow](#8-testing-workflow)
- [9. Environmental Needs](#9-environmental-needs)
  * [9.1 Base System Hardware](#91-base-system-hardware)
  * [9.2 Base Software Elements in the Test Environment](#92-base-software-elements-in-the-test-environment)
  * [9.3 Productivity and Support Tools](#93-productivity-and-support-tools)
  * [9.4 Test Environment Configurations](#94-test-environment-configurations)
- [10. Responsibilities, Staffing, and Training Needs](#10-responsibilities--staffing--and-training-needs)
  * [10.1 People and Roles](#101-people-and-roles)
  * [10.2 Staffing and Training Needs](#102-staffing-and-training-needs)
- [11. Iteration Milestones](#11-iteration-milestones)
- [12. Risks, Dependencies, Assumptions, and Constraints](#12-risks--dependencies--assumptions--and-constraints)
- [13. Management Process and Procedures](#13-management-process-and-procedures)


## 1. Introduction

### 1.1 Purpose

The purpose of the Iteration Test Plan is to gather all of the information necessary to plan and control the test effort for a given iteration. It describes the approach to testing the software.
This Test Plan for Träwelling supports the following objectives:

- Identifies the items that should be targeted by the tests.
- Identifies the motivation for and ideas behind the test areas to be covered.
- Outlines the testing approach that will be used.
- Identifies the required resources and provides an estimate of the test efforts.

### 1.2 Scope

This document describes the used tests, as well as the testing workflow. We use Code quality Tests, Unit Tests and Feature Tests. Additionally, the code is reviewed by another member of the team each PR as well as an external code quality measurement tool.

### 1.3 Intended Audience

This document is intended for internal use primarily. Further, this document will be handed in at the end of the semester and is posted on our Blog.

### 1.4 Document Terminology and Acronyms



| Abbr | Abbreviation                        |
|------|-------------------------------------|
| API  | Application Programmable Interface  |
| CI   | Continuous Integration              |
| CD   | Continuous Delivery/Deployment      |
| n/a  | not applicable                      |
| SRS  | Software Requirements Specification |
| tbd  | to be determined                    |
| UI   | User Interface                      |
| VC   | Version Control                     |
| TDD  | Test Driven Development             |
| SRS  | Software Requirements Specification |
| UCD  | Use Case Diagram                    |
| n/a  | not applicable                      |
| tbd  | to be done                          |

### 1.5  References


| Reference        | 
| ------------- |
| [Blog](https://traewelling.wordpress.com/) |
| [Github](https://github.com/traewelling/traewelling) |
| [YouTrack](https://traewelling-dhbw.myjetbrains.com/) |
| [SAD](./SoftwareArchitectureDocument.md) | 
| [SRS](./SoftwareRequirementsSpecification.md) |
| [Use Cases](./UCs) |
| [Test Plan](./TestPlan.md) |

## 2. Evaluation Mission and Test Motivation
### 2.1 Background
Testing serves to ensure that the written code does what it is intended to do. It also prevents future code changes to break existing functionality unnoticed. In the context of integration it can also prevent broken software states to be merged into secured VC branches

### 2.2 Evaluation Mission
The mission of this test plan is to prevent errors in production, find possible security risks and ensure an outstanding software quality.

### 2.3 Test Motivators
Our testing is motivated by
- quality risks
- technical risks
- use cases
- functional requirements

## 3. Target Test Items

The listing below identifies those test items (software, hardware, and supporting product elements) that have been identified as targets for testing.
This list represents what items will be tested.

Items for Testing:
- PHP Backend
- PHP (Blade) Frontend
- PHP API (JSON, REST)

## 4. Outline of Planned Tests

### 4.1 Outline of Test Inclusions
Testing static functions with UnitTests.
Testing everything else with Feature Tests.

### 4.2 Outline of Other Candidates for Potential Inclusion
Stress Testing the application and its servers. Findung security breaches.

### 4.3 Outline of Test Exclusions
Most tests require a functioning backend to the HAFAS-API. Since we have to test trains, that are travelling right now,
we need to ensure non-breaking tests around the clock. At some times of the day, there is virtually no public transport,
so we need to skip these tests if no applicable train is found (e.g. at night).

## 5. Test Approach
### 5.1 Initial Test-Idea Catalogs and Other Reference Sources
**n/a**

### 5.2 Testing Techniques and Types

#### 5.2.1 Data and Database Integrity Testing
**n/a**

#### 5.2.2 Functional Testing

|                       | Description                                                         |
|-----------------------|---------------------------------------------------------------------|
|Technique Objective    |  Logic and processes in the app should be simulated |
|Technique              |  PHPUnit Tests with PHP Faker and the Laravel testing environment |
|Oracles                |  User interacts with the app (for example enters valid data in a text field) |
|Required Tools         |  PHPUnit, XDebug, (composer dependencies) |
|Success Criteria       |  All tests pass without error |
|Special Considerations |  n/a |

#### 5.2.3 Business Cycle Testing
n/a
#### 5.2.4 User Interface Testing

|                        |                                                                            |
|------------------------|----------------------------------------------------------------------------|
| Technique Objective    | Simulating UI interactions by a user                                       |
| Technique              | UI testing                                                                 |
| Oracles                | Interactions with UI components (e.g. button click) triggers action        |
| Required Tools         | PHPUnit, XDebug, composer DEV-dependencies                                 |
| Success Criteria       | All tests pass without errors and the expected behaviour can be observed   |
| Special Considerations | -                                                                          |

#### 5.2.5 Performance Profiling
n/a

#### 5.2.6 Load Testing
n/a

#### 5.2.7 Stress Testing
n/a

#### 5.2.8 Volume Testing
n/a

#### 5.2.9 Security and Access Control Testing
n/a

#### 5.2.10 Failover and Recovery Testing
n/a

#### 5.2.11 Configuration Testing
n/a

#### 5.2.12 Installation Testing

|                       | Description                                                         |
|-----------------------|---------------------------------------------------------------------|
|Technique Objective    |   (Re-)Install the software in a controlled environment, to ensure a correct installation/upgrade-process  |
|Technique              |   Install software in a github-container each PR |
|Oracles                |   n/a |
|Required Tools         |   GitHub CI/CD |
|Success Criteria       |   No errors while installing |
|Special Considerations |   n/a |


## 6. Entry and Exit Criteria

### 6.1 Test Plan

#### 6.1.1 Test Plan Entry Criteria
Creating new PRs on GitHub will trigger the GitHub CI/CD pipeline.

#### 6.1.2 Test Plan Exit Criteria
When all tests pass without throwing an exception.

#### 6.1.3 Suspension and Resumption Criteria
n/a

### 6.2

##### 6.2.1 Test Cycle Entry Criteria
n/a

##### 6.2.2 Test Cycle Exit Criteria

n/a

##### 6.2.3 Test Cycle Abnormal Termination

n/a


## 7. Deliverables

## 7.1 Test Evaluation Summaries
The GitHub pipeline provides the results via the GitHub website, as well as via e-mail.

## 7.2 Reporting on Test Coverage
The test coverage is measured during testing and reported to Codacy. The results can be viewed in the 
Codacy webinterface. 

## 7.3 Perceived Quality Reports
n/a

## 7.4 Incident Logs and Change Requests
n/a

## 7.5 Smoke Test Suite and Supporting Test Scripts
n/a

## 7.6      Additional Work Products
n/a

### 7.6.1     Detailed Test Results
n/a

### 7.6.2     Additional Automated Functional Test Scripts
A code quality analysis is created by Codacy.

### 7.6.3     Test Guidelines
n/a

### 7.6.4     Traceability Matrices
n/a



## 8. Testing Workflow
Developers should execute tests locally before pushing source code. When creating PRs, the tests are executed automatically.

## 9. Environmental Needs
This section presents the non-human resources required for the Test Plan.
### 9.1 Base System Hardware
The following table sets forth the system resources for the test effort presented in this Test Plan.

| Resource                                                                | Quantity | Name and Type |
|-------------------------------------------------------------------------|----------|---------------|
| PHP Webserver | 1 | locally|
| Database Server                                                         |        1 | locally, mariaDB/mySQL or sqLite|
| Test Config                                                         |          | .env.testing               |

### 9.2 Base Software Elements in the Test Environment
The following base software elements are required in the test environment for this Test Plan.

| Software Element Name |  Type and Other Notes                        |
|-----------------------|----------------------------------------------|
| PHPStorm              | Test Runner / IDE                            |
| PHPUnit               | Unit testing library                         |
| XDebug                | Coverage Report                              |

### 9.3 Productivity and Support Tools
n/a

### 9.4 Test Environment Configurations
n/a

## 10. Responsibilities, Staffing, and Training Needs

### 10.1 People and Roles
tbd

### 10.2 Staffing and Training Needs
n/a

## 11. Iteration Milestones

| Milestone | Planned Start Date | Actual Start Date | Planned End Date | Actual End Date |
|---|---|---|---|---|
| Run Cucumber Tests | 30.10.2020 | 30.10.2020 | 10.06.2021 | -   |
| Having Unit Tests | 04.05.2021 | 02.11.2019   | 10.06.2021   | -   |
| Having CI in Github | 04.05.2021 | 02.11.2019 | 10.06.2021 | . |
| 50% Unit Test Coverage | 04.05.2021 | - | 09.05.2021 | - |

## 12. Risks, Dependencies, Assumptions, and Constraints
| Risk | Mitigation Strategy	| Contingency (Risk is realized) |
|---|---|---|
| Unexpected failures in production | Cover as much scenarios as possible, Logging | Look into logs and fix the bug, Roll back version if necessary |

## 13. Management Process and Procedures

n/a
