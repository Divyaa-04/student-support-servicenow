# Testing Scenarios

This document contains the main testing scenarios used during development of the Student Support & Service Request Management System.

## Incident Testing

### Scenario 1 — Student Portal Login Issue
- Caller: Max Mayfield
- Category: Software
- Initial assignment: Student Service Desk
- Escalated to: Student Application Support
- Final state: Resolved

### Scenario 2 — Computer Lab Wi-Fi Issue
- Caller: Max Mayfield
- Category: Network
- Initial assignment: Student Service Desk
- Escalated to: Student IT Support
- Configuration Item: Student-Lab-PC-01
- Final state: Resolved

### Scenario 3 — Academic Software Access Issue
- Caller: Max Mayfield
- Category: Software
- Initial assignment: Student Service Desk
- Escalated to: Student Application Support
- Final state: Resolved

## Service Catalog Testing

Test requests were submitted for:

- Software Access Request
- College Email Account Request

The submissions generated ServiceNow request and requested-item records with fulfillment tasks.

## Flow Designer Testing

The Flow Designer automation was tested using a student support incident.

The configured Send Email action executed successfully for the incident caller.

## CMDB Testing

The `Student-Lab-PC-01` Configuration Item was associated with the computer lab Wi-Fi incident.

## ATF Testing

The `Student Support Incident Test` was executed successfully.

The test included:

1. Open a new Incident form
2. Set field values
3. Submit the form
4. Query the Incident table

All four test steps completed successfully.
