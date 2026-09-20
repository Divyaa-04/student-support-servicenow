# Student Support & Service Request Management System

A ServiceNow-based student support system developed using a Personal Developer Instance (PDI).

The project simulates a college IT support environment where students can report technical issues and submit service requests. Support teams can manage incidents, provide knowledge-based assistance, process service requests, and track support activities through ServiceNow.

The project was built to gain practical experience with ServiceNow administration, IT service management, workflow automation, service catalog configuration, CMDB, reporting, and automated testing.

---

# Problem Statement

In a college environment, students may face issues such as student portal login problems, Wi-Fi connectivity issues, software access requirements, and college email requests.

The objective of this project is to create a centralized ServiceNow-based support system that allows these issues and requests to be recorded, assigned to appropriate support teams, tracked through their lifecycle, and resolved in a structured manner.

---

# Objectives

- Configure users, groups, and roles for a student support environment.
- Manage student technical issues using Incident Management.
- Create service requests using the Service Catalog.
- Create knowledge articles for common student issues.
- Configure basic workflow automation using Flow Designer.
- Create and associate a Configuration Item (CI) using CMDB.
- Build reports and a support dashboard.
- Create and execute an Automated Test Framework (ATF) test.
- Practice troubleshooting and incident escalation using realistic support scenarios.

---

# Support Workflow

The project follows a simple support workflow:

```text
Student
   ↓
Reports an Issue / Submits a Request
   ↓
Student Service Desk
   ↓
Initial Review & Troubleshooting
   ↓
 ┌───────────────────────────────┐
 │                               │
 ↓                               ↓
Student Application Support   Student IT Support
 │                               │
 ↓                               ↓
Portal / Application Issues   Hardware / Network /
                              Software / Access Issues
 │                               │
 └───────────────┬───────────────┘
                 ↓
              Resolution
```

# Support Teams

## Student Service Desk

Handles first-level support, initial troubleshooting, and ticket triage.

## Student Application Support

Handles student portal and application-related issues escalated from the Student Service Desk.

## Student IT Support

Handles hardware, network, software, and access-related issues escalated from the Student Service Desk.

---

# ServiceNow Components Used

- User and Group Management
- Incident Management
- Service Catalog
- Knowledge Management
- Flow Designer
- CMDB
- Reports and Dashboard
- Automated Test Framework (ATF)

---

# Configuration Details

## 1. Users, Groups and Roles

Created project-specific support teams and users to represent different responsibilities within the college support environment.

### Support Groups

- Student Service Desk
- Student Application Support
- Student IT Support

### Support Users

- Jane Hopper — Student Service Desk Agent
- Mike Wheeler — Student Application Support Agent
- Will Byers — Student IT Support Agent
- Max Mayfield — Student
- Dustin Henderson — Student
- Lucas Sinclair — Student
- Steve Harrington — Student

The support agents were configured with the `itil` role for incident and service management activities.

---

## 2. Incident Management

Configured and managed student support incidents through different stages of the incident lifecycle.

### Scenarios Created

- Student portal login issue
- College computer lab Wi-Fi connectivity issue
- Academic software access issue

The incidents were assigned to the Student Service Desk for initial troubleshooting and escalated to the appropriate support team when further investigation was required.

The project included:

- Incident creation
- Categorization
- Assignment to support groups
- Agent assignment
- Work notes
- Escalation
- Customer comments
- Resolution
- Resolution notes

---

## 3. Service Catalog

Created service catalog items for common student service requests.

### Software Access Request

Allows students to request software required for academic work.

Configured variables:

- Software Required
- Reason for Request
- Required By Date

### College Email Account Request

Allows students to request a college email account for academic communication.

Configured variables:

- Email Account Type
- Reason for Request
- Required By Date

Both catalog items were tested by submitting sample requests and verifying the generated request and requested-item records.

---

## 4. Knowledge Management

Created and published three knowledge articles in the IT knowledge base to provide self-service guidance for common student issues:

- KB0010001 — How to Reset a Student Portal Password
- KB0010002 — Troubleshooting College Wi-Fi Connectivity
- KB0010003 — How to Request Software Access

The articles provide step-by-step guidance for resolving common issues and requesting services through the ServiceNow platform.

---

## 5. Flow Designer

Created a Flow Designer flow named:

**Software Access Request Fulfillment**

The flow uses an Incident record trigger for a student support scenario and a **Send Email** action to notify the incident caller when a new incident is created.

The flow was activated and tested successfully using a sample student support incident.

---

## 6. CMDB

Created a Configuration Item representing a computer used in the student computer lab.

**CI:** `Student-Lab-PC-01`

Configured information included:

- Class: Computer
- Description
- Support group: Student IT Support
- Operating status: Operational
- Install status: Installed

The CI was associated with the student lab Wi-Fi incident to demonstrate linking configuration information with incident management.

---

## 7. Reports and Dashboard

Created reports to analyze resolved student support incidents.

### Reports

- Student Support Incidents by Assignment Group
- Student Support Incidents by Category

Created a dashboard named:

**Student Support Dashboard**

The dashboard provides a centralized view of student support information and incident-related data.

---

## 8. Automated Test Framework

Created an ATF test named:

**Student Support Incident Test**

The test validates the basic creation of a student support incident through the standard Incident form.

### Test Steps

1. Open a new Incident form
2. Set field values
3. Submit a form
4. Query the Incident table to verify that a matching record exists

The test was executed successfully using the Client Test Runner. Test data was rolled back after execution as part of the ATF test process.

---

# Testing Scenarios & Results

The project was tested using realistic student support scenarios to verify incident handling, service requests, automation, CMDB relationships, reporting, and automated testing.

## Incident Testing

### Scenario 1 — Student Portal Login Issue

- Caller: Max Mayfield
- Category: Software
- Initial assignment: Student Service Desk
- Escalated to: Student Application Support
- Resolution: Password reset guidance provided and portal access restored
- Final state: Resolved

### Scenario 2 — Computer Lab Wi-Fi Issue

- Caller: Max Mayfield
- Category: Network
- Initial assignment: Student Service Desk
- Escalated to: Student IT Support
- Configuration Item: `Student-Lab-PC-01`
- Resolution: Network adapter troubleshooting performed and connectivity restored
- Final state: Resolved

### Scenario 3 — Academic Software Access Issue

- Caller: Max Mayfield
- Category: Software
- Initial assignment: Student Service Desk
- Escalated to: Student Application Support
- Resolution: Required access configuration was identified and guidance was provided
- Final state: Resolved

---

## Service Catalog Testing

Test requests were submitted for:

- Software Access Request — Python
- College Email Account Request — Student Email

The submissions generated ServiceNow request and requested-item records along with catalog fulfillment tasks.

---

## Flow Designer Testing

The Flow Designer automation was tested using a student support incident.

The configured **Send Email** action executed successfully for the incident caller.

---

## CMDB Testing

The `Student-Lab-PC-01` Configuration Item was associated with the computer lab Wi-Fi incident.

This verified that a CI could be linked to an incident for configuration-related context.

---

## ATF Testing

The `Student Support Incident Test` was executed successfully.

The test validated:

1. Opening a new Incident form
2. Setting the required field values
3. Submitting the incident
4. Querying the Incident table to verify that a matching record existed

All four test steps completed successfully.

ATF test data was rolled back after execution.

---

# Technologies & ServiceNow Features

### Platform

- ServiceNow
- Personal Developer Instance (PDI)

### ServiceNow Administration

- User and Group Management
- Roles and Access Control
- Incident Management
- Service Catalog
- Knowledge Management
- CMDB
- Configuration Items
- Flow Designer
- Reports and Dashboards
- Automated Test Framework (ATF)

### Supporting Technologies

- ServiceNow Client Test Runner
- Automated Test Framework (ATF)
- GitHub
---

# Key Learnings

Through this project, I gained practical experience in:

- Configuring users, groups, and roles in ServiceNow.
- Understanding the difference between incidents and service requests.
- Managing incidents through assignment, escalation, troubleshooting, and resolution.
- Creating service catalog items with different types of variables.
- Creating and publishing knowledge articles for common support issues.
- Building a basic automation using Flow Designer.
- Creating Configuration Items and associating them with incidents.
- Creating reports and dashboards to visualize support information.
- Creating and executing automated tests using ATF.
- Troubleshooting configuration and workflow issues while working with a ServiceNow PDI.

---

# Project Screenshots

Screenshots demonstrating the ServiceNow configuration and testing performed during the project are available in the `screenshots` folder.

---

# Project Structure

```text
student-support-servicenow/
│
├── README.md
│
└── screenshots/

---
```

# Project Status

**Completed**

This project was developed and tested using a ServiceNow Personal Developer Instance as a hands-on learning and portfolio project.

---

# Author

**Divya Thota**

B.Tech — Electrical & Electronics Engineering  
Pragati Engineering College, 2021–2025

**ServiceNow Certified System Administrator (CSA)** — July 2025

**Virtual Internship Experience**
- ServiceNow Virtual Intern — SmartBridge in collaboration with AICTE & ServiceNow
- AWS Data Analytics Virtual Intern — AWS Academy / AICTE EduSkills

This project was developed as part of my hands-on learning journey in ServiceNow administration and IT service management.
