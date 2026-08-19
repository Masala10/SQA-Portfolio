API Testing Project
SQA Portfolio - API Testing

This repository contains my manual API testing portfolio using Postman. 
It demonstrates test case design, bug discovery, and bug reporting for REST APIs.

Project Overview
API Tested: [FakeStoreAPI](https://fakestoreapi.com) - A free fake REST API for e-commerce
Tool Used: Postman
Focus: Negative Testing, Status Code Validation, Data Integrity

Test Coverage
| Test Case | Method | Endpoint | Status |
| --- | --- | --- | --- | --- |
| 1 | Get Product by Valid ID | GET | /products/1 | Pass |
| 2 | Get Product by Invalid ID | GET | /products/9999 | Fail - Bug Found |
| 3 | Create Product with Invalid Data | POST | /products | Fail - Bug Found |
| 4 | Delete Product and Verify | DELETE | /products/21 | Fail - Bug Found |

Bugs Found

API-BUG03: DELETE Does Not Actually Delete Resource
Severity: High  
Expected: After DELETE, GET should return 404 Not Found  
Actual: GET still returns 200 OK. Data persists.  
Evidence: ![Bug 03](evidence-api-bug03.png)

API-BUG02: No Input Validation on POST
Severity: Critical  
Expected: API should return 400 Bad Request for invalid data  
Actual: API returns 201 Created with empty title and string price  
Evidence: ![Bug 02](evidence-api-bug02.png)

PI-BUG01: Wrong Status Code for Invalid GET
Severity: High  
Expected: GET /products/9999 should return 404 Not Found  
Actual: API returns 200 OK  
Evidence: [Screenshot to be added]

How I Test
1.  Positive Testing: Verify happy path works
2.  Negative Testing: Send invalid data, invalid IDs, wrong methods
3.  Automation in Postman: Using `pm.test()` and `pm.expect()` for assertions
4.  Bug Reporting: Document with Steps, Expected vs Actual, Severity, and Evidence

Skills Demonstrated
- REST API Testing with Postman
- Writing JavaScript Assertions in Postman
- Bug Reporting with Severity and Impact
- Negative Test Case Design
- API Status Code Validation

Next Steps
Adding collection files and Newman CLI reports soon.
