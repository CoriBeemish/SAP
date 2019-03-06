# SAP

> I've started this repository to document and follow my journey through studying SAP and SAP ABAP. Below are the resources I've
> used and swaths of information I've gathered to hopefully help other people on the same journey. 

## Table of Contents
- [What is SAP?](#what-is-sap)
- [Why SAP?](#why-sap)
- [SAP Basics](#sap-basics)
  - [SAP Architecture](#sap-architecture)
  - [SAP Work Processes]()
- [Transaction Codes](#transaction-codes)
- [Flashcard List](#flashcard-list)
- [Resources](#resources)
  - [Tutorials](#tutorials)
  - [Websites](#websites)
  - [Videos](#videos)

## What is SAP?

SAP (**S**ystems, **A**pplications & **P**roducts for Data Processing) is an integrated suite of applications and modules designed to 
work together to handle data processing for large companies. SAP R/1 (the first version of SAP) was first developed in Germany in 1972.
SAP is compatible with multiple platforms and operating systems such as Microsoft Windows and UNIX. 

## Why SAP?

SAP provides ERP (Enterprise Resource Planning) solutions and services. ERP is software that is built to support businesses and organizations in different industries, no matter their size or strength. The ERP package is designed to support and integrated every functional area of a business process such as procurement of goods and services, sale and distribution, finance, accountings, human resource, manufacturing, production planning, logistics & warehouse management. 
ERP allows a business to be connected and integrated, which allows for efficient information flow from one business process to another as soon as information is entered into the system. This also allows automation of business processes of management, operational, and supporting processes. 

## SAP Basics

### SAP Architecture
<details>
  <summary> SAP Architecture </summary>

The current verison of SAP software is known as SAP ERP Central Component (ECC). Previously, it was SAP R/3, where the R stood for "Real-time data processing" and the "3" was for "3-tier". The three tiers of SAP are:
  - The Presentation Layer/Server
  - The Application Layer/Server
  - The Database Layer/Server

The presentation layer of SAP consists of the SAP GUI


  
The sole purpose of R/3 is to provide a suite of tightly integrated, large-scale business applications. The standard functional modules
shipped with the standard SAP package are the following:
- PP (Production Planning)
- MM (Materials Management)
- SD (Sales and Distribution)
- FI (Financial Accounting)
- CO (Controlling)
- AM (Fixed Assets Management)
- PS (Project System)
- WF (Workflow)
- IS (Industry Solutions)
- HR (Human Resources)
- PM (Plant Maintenance)
- QM (Quality Management)
  </details>

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
- What is SAP's current development platform?
  - NetWeaver
- What does NetWeaver support?
  - ABAP and JAVA
- What are the advantages of SAP's Real-Time Processing?
  - Immediate data processing across all interconnected processes, efficient and less time-consuming execution of transactions, and quicker order turnarounds and product to market
- What is SAP R/3 also called?
  - SAP ERP Central Component (ECC)
- What type of architecture does SAP have?
  - 3-tier client/server architecture
- What are the advantages of SAP's client-server architecture?
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
- https://help.sap.com/viewer/index
- https://www.tutorialspoint.com/sap
- https://en.wikipedia.org/wiki/SAP_SE (No joke! I actually learned a lot through Wikipedia about SAP and its systems. Wiki definitley earned its $4 donation!)
- Udemy's SAP ABAP courses by Peter Moxon
- https://erproof.com/abap/
