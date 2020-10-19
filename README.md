# Software Requirements Specification

## Table of contents
- [Table of contents](#table-of-contents)
- [Introduction](#1-introduction)
    - [Purpose](#11-purpose)
    - [Scope](#12-scope)
    - [Definitions, Acronyms and Abbreviations](#13-definitions-acronyms-and-abbreviations)
    - [References](#14-references)
    - [Overview](#15-overview)
- [Overall Description](#2-overall-description)
    - [Vision](#21-vision)
    - [Use Case Diagram](#22-use-case-diagram)
- [Specific Requirements](#3-specific-requirements)
    - [Functionality](#31-functionality)
    - [Usability](#32-usability)
    - [Reliability](#33-reliability)
    - [Performance](#34-performance)
    - [Supportability](#35-supportability)
    - [Design Constraints](#36-design-constraints)
    - [Online User Documentation and Help System Requirements](#37-on-line-user-documentation-and-help-system-requirements)
    - [Purchased Components](#purchased-components)
    - [Interfaces](#39-interfaces)
    - [Licensing Requirements](#310-licensing-requirements)
    - [Legal, Copyright And Other Notices](#311-legal-copyright-and-other-notices)
    - [Applicable Standards](#312-applicable-standards)
- [Supporting Information](#4-supporting-information)

## 1. Introduction

### 1.1 Purpose
This Software Requirements Specification was created to collect and organize the requirements for the _Träwelling_ website.
It includes a thorough description of the expected functionality for the project, as well as the nonfunctional requirements.
These are crucial for the purposes of establishing the understanding between the suppliers of the software and the customers,
as well as minimizing the risks connected to the misinterpreting customer’s expectations. The document will furthermore
provide the basis for costs-estimation and later validation of the results achieved.

### 1.2 Scope
This SRS applies to the entire _Träwelling_ project. _Träwelling_ is a free Website for tracking and sharing your träwelling expirinces by bus, sub and train.

ACTORS: There are two types of actors: **träwellers** and **general visitors**

 - Träweller: Person that is registered on the website.
 - General visitor: Person whos just passing by.

SUBSYSTEMS:
 - *membership*: Register or terminate membership
 - *check in*: Register a trip and share it.
 - *basic interaction*: Have a look at profiles, trips, posts, blog, a list of active träwellers and the leaderboard.

### 1.3 Definitions, Acronyms and Abbreviations

| Abbrevation |                                        |
| ----------- | -------------------------------------- |
| SRS         | Software Requirements Specification     |
| UC          | Use Case                               |
| n/a         | not applicable                         |
| tbd         | to be determined                       |
| FAQ         | Frequently asked Questions             |
| HTTP	      | Hyperrext Transfer Protocol            |
| HTTPS       | HTTP Secure                            |
| REST        | Representational state transfer        |
| API         | application programming interface      |
| MVC         | Model, View, and Controller            |
| MIT         | Massachusetts Institute of Technology  |
| PHP         | PHP: Hypertext Preprocessor            |
| AGPL        | Affero General Public License           |
| UI          | User Interface                         |
| SQL         | Structured Query Language              |


| Definition                          |     |
| ----------------------------------- | --- |
| Software Requirements Specification | a document, which captures the complete software requirements for the system, or a portion of the system. |
| Use Case                            | a list of actions or event steps, typically defining the interactions between a role (known in the Unified Modeling Language as an actor) and a system, to achieve a goal. |

### 1.4 References

| Title                                                              | Date       | Publishing organization   |
| -------------------------------------------------------------------|:----------:| ------------------------- |
| [Träwelling Blog](https://traewelling.wordpress.com/)              | 2020-10-17 | Träwelling Team             |
| [GitHub - Repository](http://github.com/traewelling/traewelling)   | 2020-10-17 | Träwelling Team             |
| [Träwelling Twitter](https://twitter.com/traewelling)              |            | Träwelling Team           |  


### 1.5 Overview
The remainder of this document is structured in the following way: In the next chapter, the Overall Description section,
an overview of the functionality of the product and an use-case-diagram is given. The third chapter, the Requirements
Specification section, provides an more detailed description of the requirements. In order to achieve a high level of
specification in defining the requirements, all functions presented in the diagram are separated into subsections of
section "3.1 Functionality". Further requirements like usability and supportability are listed in chapters 3.2 through
3.12. Supporting information is given in chapter four.

## 2. Overall Description

### 2.1 Vision
We love trains. We want to give everyone the joy of tracking their travels and share them with other people

### 2.2 Use Case Diagram
![Träwelling Use Case Diagram][UseCaseDiagram]


## 3. Specific Requirements

### 3.1 Functionality
This section will list all functional requirements for _Träwelling_ and explain their functionality. Each of the following
subsections represents a subsystem of our application.

#### 3.1.1 Membership
A user has to create an account to be able to use _Träwelling_ fully. They will need to register either via mail and password or via social media (e.g. Twitter, Mastodon, Apple, etc.).

#### 3.1.2 Check in


### 3.2 Usability
We plan on designing the frontend as intuitive and self-explanatory as possible to make the user feel as comfortable
as possible visiting the website.

#### 3.2.1 No training time needed
Our goal is that a user visits the website, see’s the landing page and is able
to use all features without any explanation or help.

#### 3.2.1 Natural workflow
The workflow should reflect the real life and not work against it. If a specific order of tasks is widespread,
then the website should do it in the same way. 

### 3.3 Reliability

#### 3.3.1 Availability and MTTR
The server shall be available at least 95% of the time which is equivalent to ca. 1 hour downtime a day. Downtime is tolerable
during nighttime as it is very unlikely that users upload or change data at night. But the server must be available during
"rush hours" when most people go are travelling. The time to repair bugs should be as low as possible.

#### 3.3.2 Defect Rate
 - The amount of bugs should be kept at a minimum
   - Bugs should be fixed as soon as possible if they're a security issue
 - Loss of data
   - Incremental backups should be kept at a daily rate, full backups at a weekly rate

### 3.4 Performance

#### 3.4.1 Response time
Should be as low as possible. Maximum response time is 10 seconds. Average response time should be less than 3 seconds. 

#### 3.4.2 Capacity
The system should be capable to manage thousands of registered users and up to hundred users at the same time on one server.
If the capacity exceeds that number, it should be possible to scale and use more servers.

#### 3.4.3 Connection Bandwidth
The size of data to be synchronized between the server and client should be minimal, e.g. renaming an item must not lead to
downloading all of existing data on the server.

### 3.5 Supportability

#### 3.5.1 Coding standards
In order to maintain supportability and readability of our code, we will try to adopt the latest clean code standard as far as
possible and use the [Google Java Style Guide][GoogleGuidelines] for naming conventions, formatting and programming
practices throughout the project with a few additions:
  - lineLimit of 120
  - opening bracket of classes in a newline
  - opening bracket of new methods in the same line

This will also be defined in the `phpcs.xml`.

#### 3.5.2 Maintenance Utilities
In order to test language and platform versions, a continuous integration service is required which runs tests on
combinations of platform and language versions.

### 3.6 Design Constraints
We are focused on providing a modern design regarding both code and application.

As _Träwelling_ is an website, the chosen programming language is PHP. The MVC architecture shall be used to
differentiate between UI and the actual logic.

The server's operating system must support MySQL and programs compiled using PHP. A RESTful API shall be used to communicate between frontend and backend.

Therefore following platforms and language must be supported.
 – PHP with the framework laravel
 – Package management npm and composer

### 3.7 On-line User Documentation and Help System Requirements
Our goal is to make our website as intuitive as possible. Nevertheless a help system will be created that contains FAQs, etc.
This might be helpful to users that do not yet use our website but want to know how it works.

### 3.8 Purchased Components
A server hosted a https://netcup.de will be rent to run the server application.  
Currently there are no other purchased components.

### 3.9 Interfaces

#### 3.9.1 User Interfaces
There will be the following user interfaces implemented which also will be available in the android application:
 - **Registration screen** showing input fields to create an account
 - **Dashboard screen**
   - shows a hitlist with posts of followings/all users
 - **Checkin screen**
 - **Profile screen**
 - **Leaderboard**
#### 3.9.2 Hardware Interfaces
n/a

#### 3.9.3 Software Interfaces
_Träwelling_ should be accessible with all modern browsers.

#### 3.9.4 Communications Interfaces
The browser will connect to the server over `HTTPS` on port `443`. An unencrypted connection over `HTTP` on port `80` shall not be supported.

### 3.10 Licensing Requirements
The project will be licensed with the [AGPL-3.0](https://www.gnu.org/licenses/agpl-3.0.en.html) License. Used packages should not conflict with this License. Preferrably packages with the MIT License should be used.

### 3.11 Legal, Copyright, and Other Notices
The _Träwelling_ team will not take any responsibility for incorrect bills or lost data. The _Träwelling_ logo
may only be used for the official _Träwelling_ website.

### 3.12 Applicable Standards
The following Clean Code standards are going to be applied to the code as far as possible:
 1. Intuitive names of variables and methods.
 2. Comply with coding conventions of the language of choice ([Google Java Style Guide][GoogleGuidelines]).
 3. Comments used to navigate through the code but not polluting it.
 4. Design patterns integration.
 5. Each method does one thing and does it well.
 6. No hard-coded strings.
 7. No premature optimization.


## 4. Supporting Information

**For more information contact:**
 - Levin Baumann
 - Thomas Englert
 - Marius Holwein

[UseCaseDiagram]:   traewelling.png
[GoogleGuidelines]: https://google.github.io/styleguide/javaguide.html

