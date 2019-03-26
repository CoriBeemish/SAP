# SAP

> I've started this repository to document and follow my journey through studying SAP and SAP's programming language, ABAP. Below are my notes and my collection of resources I've used to study. Hopefully my notes might help other people on the same journey. 
 
## Table of Contents
- [What is SAP?](#what-is-sap)
- [Why SAP?](#why-sap)
  - [SAP Modules](#sap-modules)
- [SAP Basics](#sap-basics)
  - [SAP Architecture](#sap-architecture)
  - [Client-Dependent vs. Client-Independent](#client-dependent-vs-client-independent)
- [SAP BASIS](#sap-basis)
- [SAP ABAP](#sap-abap)
  - [SAP ABAP Certification Rubric](#sap-abap-certification-rubric)
  - [ABAP Workbench Foundations](#bc400-abap-workbench-foundations)
- [Transaction Codes](#transaction-codes)
  - [What is a transaction code?](#what-is-a-transaction-code)
- [Flashcard List](#flashcard-list)
- [How I installed my own SAP instance](#how-i-installed-my-own-sap-instance)
- [Resources](#resources)
  - [Tutorials](#tutorials)
  - [Websites](#websites)
  - [Videos](#videos)

## What is SAP?

SAP (**S**ystems, **A**pplications & **P**roducts for Data Processing) is an integrated suite of applications and modules designed to 
work together to handle data processing for large companies. SAP R/1 (the first version of SAP) was first developed in Germany in 1972.
SAP is compatible with multiple platforms and operating systems such as Microsoft Windows and UNIX. 

## Why SAP?

SAP provides ERP (Enterprise Resource Planning) solutions and services, which is a package built to support businesses and organizations in different industries of any size. The ERP package is designed to support and integrate every functional area of a business such as procurement of goods and services, sales and distribution, finance, accounting, human resources, manufacturing, production planning, logistics, & warehouse management. The following are some of the colutions SAP offers in it's *mySAP Business Suite*:
- SAP customer relationship management (CRM)
- SAP Enterprise Resource Planning (ERP)
- SAP product lifecycle management (PLM)
- SAP supplier relationship management (SRM)
- SAP supply chain management (SCM) 

ERP allows a business to be connected and integrated, which allows for efficient information flow from one business process to another as soon as information is entered into the system. This also allows automation of business processes of management, operational, and supporting processes. SAP offers various **functional modules**, also known as **functional areas**, some of which are the following:
- Financial Accounting (FI)
- Financial Supply Chain Management (FSCM)
- Controlling (CO)
- Materials Management (MM)
- Sales and Distribution (SD)
- Logistics Execution (LE)
- Production Planning (PP)
- Quality Management (QM)
- Plant Maintenance (PM)
- Project System (PS)
- Human Resources (HR)

**Advantages of ERP**
- Saves time and expenses.
- Allows faster decision-making by the management, utilizing the data and reporting tools designed in the systems.
- Single data source and sharing of data among all the units of an organization.
- Helps in tracking every transaction that takes place in an organization, from starting till end.
- Supplies real-time information whenever required.
- Provides synchronized information transfer in between different functional areas such as sales, marketing, finance, manufacturing, human resource, logistics, etc.

**Disadvantages of ERP**
- It is not always easy to incorporate ERP in an organization.
- Sometimes business processes critical to an organization are to be re-engineered to align them with an ERP solution.
- Cost of complex integration can be very high.
- Switching from one ERP solution to another increases the implementation cost even further.
- End-users are to be trained for their daily operations.
- Customization is not preferred.

SAP's ERP package is called ECC (**E**nterprise **C**entral **C**omponent).

### NetWeaver
In SAP's business suite solutions, they also offer SAP NetWeaver, which allows the user to access SAP's systems to enter and display data. SAP NetWeaver is the technical foundation on which almost all mySAP solutions are developed from. SAP NetWeaver provides people integration, information integration, process integration, and application platform.
Integration Layer: People Integration
SAP NetWeaver is an enterprise portal that allows multiple users to log into SAP's system and view, edit, and enter data into multiple different business processes. The core functions of SAP Enterprise Portal are written in Java, so you would need a J2EE runtime environment such as the one provided by the SAP Web Application Server Java.


### SAP Modules

## SAP Basics

### SAP Architecture

SAP's based its R/3 architecture on a three-tier client/server model. The R in "R/3" stands for "Real-time data processing" and the "3" is for "3-tier". The three tiers of SAP are from high to low levels:
  - The Presentation Layer/Server
  - The Application Layer/Server
  - The Database Layer/Server

The presentation server is also known as the client layer. In the presentation layer, the user uses the SAP GUI to interact with the SAP system. SAPGUI accepts inputs from the user and sends these requests to the Application server for processing. The application server sends the results back to the SAPGUI which formats the output for display.

The application server is also known as the Kernel Layer and Basic Layer. All SAP application programs are executed in the application layer. The application layer serves as the communicator between the presentation layer and the database layer. The components of an application server consists of a dispatcher and multiple work processes. All requests that come in from the presentation server are directed first to the dispatcher. Each request sent to the dispatcher writes them to the dispatcher queue which works on a first-in, first-out basis, thus each request is allocated to the first available work process one at a time. To perform any processing for a user's request, a work process needs to address two special memory areas: the user context and the program roll area.
- The user context is a memory area that contains information about the user such as a user's current settings, a user's authorizations, and the names of the programs the user is currently running. When a user logs on, a user context is allocated for that logon. When they log off, that user context is freed.
- Each time a user starts a program, a roll area is created for that instance of that program. The roll area is a memory area that contains information about the programs execution, such as the values of the variables, the dynamic memory allocations, and the current program pointer. If two users run the same program at the same time, two roll areas will exist, one for each user. The roll area is freed when the program ends. 
- There are seven types of work processes. Each handles a specific type of request.
  - D (Dialog): Dialog requests
  - V (Update): Requests to update data in the database
  - B (Background): Background jobs
  - S (Spool): Print spool requests
  - E (Enqueue): Logical lock requests
  - M (Message): Routes messages between application servers within an R/3 system
  - G (Gateway): Funnels messages into and out of the R/3 system

The database server stores all of the data of an SAP enterprise system. Each SAP system has a central database in which the entire dataset is stored. Not only the application data, but also all the administration data, customization settings, ABAP source code, etc. are stored here. EVERYTHING is stored in the database. The software component responsible for the database layer consists of the RDBMS and the actual database. The **RDBMS** (Relation Database Management System) sends the data back to the database server, which then passes the information back to the application server. The application server in turn passes that information to your ABAP program.
- ABAP/4 code is portable between databases. To access the database of an ABAP program, you will need to code SAP's Open SQL, which is a subset and variation of SQL. The ABAP interpreter passes all Open SQL statements to the database interface as part of the work process. There is it converted to SQL, which is native to the installed RDMS.

### Client-Dependent vs. Client-Independent

A client is a logical portion of an SAP R/3 physical database. From a business standpoint, a client can be interpreted as a logical group of companies. All customization, configuration, and development are all done in SAP in a client. More information about client usage below.
The data from customizing and development may be stored within an individual client (client-dependent data) or amongst all clients (client-independent data) in the SAP system.
- Client-dependent data is defined as data specific to an individual client. Examples of client-dependent data include number ranges, ABAP variants, and user masters as well as the data that is created or updated through SAP R/3 transactions.
- Client-independent data can be defined as data contained across all clients in the system. Examples of client-independent data include data dictionary objects (tables, views), ABAP source code, screens, and menus.

A table viewed by the data dictionary in an R/3 database is client-dependent if the first field is of type CLNT and the field is names MANDT. Otherwise, the table is client-independent. 

## SAP BASIS
Basis is like an operating system for R/3. It sits between the ABAP code and the computer's operating system. It's "middleware" for SAP. 
SAP also provides a suite of tools for administering the Basis system. These tools perform tasks such as system performance monitoring, configuration, and system maintenance. 
Basis is designed to run in a client/server configuration. 


## SAP ABAP
ABAP is the programming language used by SAP to develop business application support and development. It only runs inside SAP's ABAP runtime environment. APAB is an event-driven programming language where user actions and system events control the execution of an application. 
ABAP is also called ABAP/4. The "4" in ABAP/4 stands for "fourth generation language". 

### SAP ABAP Certification Rubric
- BC400 ABAP Workbench Foundations
- BC401 ABAP Objects
- BC402 Advanced ABAP
- BC405 Programming ABAP Reports
- BC410 Developing Screen-Based User Dialogs
- BC414 Programming Database Changes
- BC425 Enhancements and Modifications
- BC427 Enhancement Framework
- BC430 ABAP Dictionary
- NET310 Fundamentals of Web Dynpro for ABAP
- NW001 SAP NetWeaver – Overview

### SAP ABAP Basics
SAP ABAP is a typed object-oriented programming language that is platform-independent. It's meant for dialog-based business applications and to support type-specific processing of data, ABAP supports type converstions and type casting. This also enables AVAP to develop multi-language applications. To ensure that SAP can continue being reliable and scalable, applications implemented in ABAP will also be able to run in future releases and thus it is upward-compatible.

All ABAP programs are made up of individual statments, always starting with a ABAP keyword and ending with a period. Statements can be indented and you can put multiple ABAP statements onto a single line. ABAP is not case-sensitive, but you do need a space between each word for an ABAP statement to work properly. You can combine consecutive ABAP statements with a colon :. Start with an ABAP keyword followed by a colon and then list the operands of the statements, seperated by commas. End the combined statement with a period just like you would with a single statement. 

Comment lines are introduced with an asterisk *. Asterisks are used for comments on a single line. For an inline comment, you must use doulbe quotation marks ".


## Transaction Codes
- ABAP Dictionary - **SE11**
- ABAP Editor - **SE38**

## Flashcard List

- **What does SAP stand for?**
  - Systems, Applications, & Products in Data Processing
- **When was SAP first released?**
  - 1992
- **SAP has what three essential elements?**
  - Real-time processing, Standard Software, and Integration of components
- **What does ABAP stand for?**
  - Advanced Business Application Programming
- **What is SAP ABAP?**
  - An ERP programming language
- **What is SAP's object-oriented extension to ABAP called?**
  - ABAP Objects 
- **What is SAP "Real-Time Processing"?**
  - Actions that immediately effect enterprise-wide business processes across all SAP modules
- **What is SAP "Standard Software"?**
  - Market product standard version of SAP software that is customizable during implementation/installation to the client's specifications
- **What is SAP "Integration"?**
  - Data and module integration for all existing business processes in an enterprise
- **What is SAP's current development platform?**
  - NetWeaver
- **What does NetWeaver support?**
  - ABAP and JAVA
- **What are the advantages of SAP's Real-Time Processing?**
  - Immediate data processing across all interconnected processes, efficient and less time-consuming execution of transactions, and quicker order turnarounds and product to market
- **What is SAP R/3 also called?**
  - SAP ERP Central Component (ECC)
- **What type of architecture does SAP have?**
  - 3-tier client/server architecture
- **What are the advantages of SAP's client-server architecture?**
  - Utilizing centrailized data resources helps reduce processing time, integrating various applications provides a seamless business environment, and allows usage of different hardware and OS on the server
- What are the 3-tiers of SAP?
  - Presentation layer, application layer, and database layer
- What is the presentation layer in SAP?
  - The user interface, the SAP GUI
- What is the application layer in SAP?
  - It's where ABAP code is interpreted
- What is the database layer in SAP?
  - It's where the data for the SAP system resides
- **What does SAP CRM stand for?**
  - Customer Realationship Management
- **What does SAP SRM stand for?**
  - Supplier Relationship Management
- **What does SAP PLM stand for?**
  - Product Lifecyle Management
- **What does SAP SCM stand for?**
  - Supply Chain Management
- **What allows users to access the SAP platform?**
  - SAP NetWeaver
- What is an SAP transaction? 
  - The execution of a program
- What does EWM stand for?
  - Extended Warehouse Management
- What are the advantages of standard SAP?
  - Maximizes SAP's efficiency and capabilities, leverage continuous optimizations and enhancements, and reduces the cost of customization, maintenance, and additonal development
- What are the advantages of customized SAP?
  - SAP is customized for one specific customer/client, able to maintain unique business identifiers and orientations, and reduced training cost
- What are the advantages of SAP Industry Solutions?
  - SAP is developed specifically for one industry, able to leverage pre-definied product already tailored to your industry, and reduced training cost
- **What does SAP CPS stand for?**
  - Central Process Scheduling
- **What is SAP CPS?**
  - An event-driven process scheduler incorporated into SAP ERP components
- **SAP CPS is a component of what?**
  - SAP NetWeaver
- **What does the “R” stand for in SAP R/3?**
  - Real-time data processing
- **What does the “3” in SAP R/3 represents?**
  - The three tiers of SAP's client/server structure
- **SAP customised software can be described as:**
  - A product for one specific client
- **Can SAP settings can be mapped and configured without writing code?**
  - Yes
- Executing a SAP transaction has the following effect:
  - Triggers a process that can cover several business areas
- The SAP Business Suite includes:
  - SAP ERP, SCM, CRM, SRM, and PLM products
- SAP’s Core Application includes:
  - Accounting, Human Resources, and Logistics
- Is SAP ERP (Enterprise Resource Planning) is SAP’s Core Application?
  - Yes
- What are the business processes included in SAP ERP?
  - Operations (Sales & Distribution, Materials Management, Production Planning, Logistics Execution, and Quality Management)
  - Financials (Financial Accounting, Management Accounting, Financial Supply Chain Management)
  - Human Capital Management (Training, Payroll, e-Recruiting)
  - Corporate Services (Travel Management, Environment, Health and Safety, and Real-Estate Management)
- What are the business processes included in SAP ERP Operations?
  - Sales & Distribution
  - Materials Management
  - Production Planning
  - Logistics Execution
  - Quality Management
- What are the business processes included in SAP ERP Financials?
  - Financial Accounting
  - Management Accounting
  - Financial Supply Chain Management
- What are the business processes included in SAP ERP Human Capital Management?
  - Training
  - Payroll
  - e-Recruiting
- What are the business processes included in SAP ERP Corporate Services?
  - Travel Management
  - Environment
  - Health and Safety
  - Real-Estate Management
- What does SAP BASIS stand for?
  - Business Application Software Integrated Solution
- What is SAP BASIS also known as?
  - SAP NetWeaver System Administration
- What is SAP BASIS?
  - The technical foundation that enables SAP applications to function
- What does SAP BASIS consist of?
  - Middleware programs and tools that support the interoperability and portability of SAP applications across systems and databases.
- What is ABAP Workbench?
  - A set of programs for developing ERM applications that run in the R/3 subsystem from SAP. 
- Is SAP ABAP a high or low-level language?
  - High-Level
- Where do ABAP programs reside?
  - Inside the SAP database
- Inside the database, what two forms does ABAP code exist as?
  - Source code & generated code
- What is ABAP source code?
  - Code that can be viewed and edited with the ABAP workbench tools.
- What is ABAP generated code?
  - A binary representation of ABAP source code. If you are familiar with Java, this generated code is somewhat comparable with Java byte code.
- You can consider SAP's run-time system as what?
  - A virtual machine, similar to Java's virtual machine
- What is a key component of ABAP's run-time system?
  - The database interface that turns database independent statements (Open SQL) into the statements understood by the underlying database (Native SQL). 
- What is a decentralized system in an enterprise? 
  - Data is maintained locally at the individual departments and do not have access to information or data of other departments
- What is a centralized system of information and data management?
  - Data is maintained at a central location and is shared with various departments and departments have access to information or data of other departments
- SAP modules can be categorized into what?
  - Functional modules & technical modules
- What is mySAP?
  - A suite of products from SAP including SAP R/3.
- How do you say "SAP"?
  - "ess-ay-pea"
- Organizational levels are structures that represent what in ECC?
  - The legal or organizational views of a company
- What are the organizational levels in ECC?
  - Client
  - Company Code
  - Plant
  - Storage Locations
  - Purchasing Organization/Purchasing Group
- What is the "Client" organizational level? 
  - A combination of legal, organizational, business and/or administrative units with a common purpose
- What is the "Company Code" organizational level?
  - Represents an independent accounting unit within a client, has it’s own balance sheet, profit and loss statement
- What is the "Plant" organizational level?
  - A manufacturing facility or branch within a company, that subdivides an enterprise from the viewpoints of production, procurement, and materials planning
- What is the "Storage Location" organizational level?
  - An organizational unit that facilitates the differentiation of stocks of materials within a plant
- What is the "Purchasing Organization" organizational level?
  - It procures materials or services, negotiates conditions of purchase with vendors, and assumes responsibility for these transactions
- What is the "Purchasing Group" organizational level?
  - A key buyer or a group of buyers who is/are responsible for certain purchasing activities
- What are application modules written in?
  - ABAP
- ABAP is interpreted by what?
  - BASIS executables
- What do Basis executables run on?
  - The operating system
- What is the purpose of R/3?
  - The sole purpose of an R/3 system is to provide a suite of tightly integrated, large-scale business applications.
- What does PP stand for?
  - Production Planning
- What does MM stand for?
  - Materials Management
- What does SD stand for?
  - Sales and Distribution
- What does FI stand for?
  - Financial Accounting
- What does CO stand for?
  - Controlling
- What does AM stand for?
  - Fixed Assets Management
- What does PS stand for?
  - Project System
- What does WF stand for?
  - Workflow
- What does IS stand for?
  - Industry Solutions
- What does HR stand for?
  - Human Resources
- What does PM stand for?
  - Plant Maintenance
- What does QM stand for?
  - Quality Management
- Are "function areas", "application areas", and "functional modules" terms synonymous with each other? 
  - Yes
- How many database tables are shipped with the standard delivery of R/3?
  - Around 8,000
- What is the standard set of applications delivered with each R/3 system?
  - PP, MM, SD, FI, CO, AM, PS, WF, IS, HR, PM, and QM
- Is ABAP case sensitive? 
  - No
- What does every ABAP start and end with?
  - Every statement begins with a keyword and ends with a period.
- What is a transaction code?
  - A transaction code is a 3 or 4 character code associated with a transaction. 
- What is a tcode?
  - A transaction code
  

## Resources

### Websites
- https://help.sap.com/viewer/index
- https://www.tutorialspoint.com/sap
- https://en.wikipedia.org/wiki/SAP_SE 
- https://erproof.com/abap/

### Videos
- Udemy's SAP ABAP courses by Peter Moxon

