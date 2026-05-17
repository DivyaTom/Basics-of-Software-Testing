# 🧪 Software Testing – Basics Notes

> A comprehensive reference for understanding the fundamentals of software testing.

---

## 📌 Table of Contents

1. [What is Software Testing?](#1-what-is-software-testing)
2. [Why is Testing Important?](#2-why-is-testing-important)
3. [Types of Testing](#3-types-of-testing)
4. [Levels of Testing](#4-levels-of-testing)
5. [Testing Techniques](#5-testing-techniques)
6. [Test Case Writing](#6-test-case-writing)
7. [Bug / Defect Life Cycle](#7-bug--defect-life-cycle)
8. [Software Development & Testing Models](#8-software-development--testing-models)
9. [Key Testing Concepts](#9-key-testing-concepts)
10. [Common Testing Tools](#10-common-testing-tools)

---

## 1. What is Software Testing?

**Software Testing** is the process of evaluating and verifying that a software application or system:
- Does what it is **supposed to do** (meets requirements)
- Does **not** do what it is not supposed to do
- Is **free of defects** (or has known, acceptable defects)

### Goals of Testing
- Find **bugs/defects** early
- Ensure **quality** of the software
- Verify **functionality**, **performance**, and **security**
- Build **confidence** in the product before release

---

## 2. Why is Testing Important?

| Reason | Description |
|--------|-------------|
| **Cost Saving** | Bugs found early are cheaper to fix |
| **User Satisfaction** | Quality software leads to happy users |
| **Security** | Testing uncovers vulnerabilities |
| **Reliability** | Ensures the software works consistently |
| **Compliance** | Some industries require verified software (e.g., healthcare, finance) |

> **Fact:** The cost of fixing a bug increases significantly the later it is found in the development cycle.

---

## 3. Types of Testing

### 3.1 Functional Testing
Tests **what** the system does — verifies that the software behaves according to requirements.

| Type | Description |
|------|-------------|
| **Unit Testing** | Tests individual functions/modules |
| **Integration Testing** | Tests interaction between modules |
| **System Testing** | Tests the complete, integrated system |
| **Acceptance Testing (UAT)** | Validates software with end-users |
| **Regression Testing** | Re-tests after changes to ensure nothing is broken |
| **Smoke Testing** | Quick check that the basic build works |
| **Sanity Testing** | Focused check after a minor fix |

### 3.2 Non-Functional Testing
Tests **how** the system performs under various conditions.

| Type | Description |
|------|-------------|
| **Performance Testing** | Speed, responsiveness under load |
| **Load Testing** | Behavior under expected load |
| **Stress Testing** | Behavior under extreme load |
| **Security Testing** | Identifies vulnerabilities |
| **Usability Testing** | Evaluates user experience |
| **Compatibility Testing** | Works across browsers, OSes, devices |
| **Scalability Testing** | Handles growth in users/data |

### 3.3 Maintenance Testing
| Type | Description |
|------|-------------|
| **Regression Testing** | After code changes |
| **Re-testing** | Re-running failed test cases after fixes |

---

## 4. Levels of Testing

```
         ┌─────────────────────────────┐
         │     Acceptance Testing      │  ← User/Business Level
         ├─────────────────────────────┤
         │      System Testing         │  ← Full Application
         ├─────────────────────────────┤
         │    Integration Testing      │  ← Module Interaction
         ├─────────────────────────────┤
         │       Unit Testing          │  ← Individual Functions
         └─────────────────────────────┘
```

| Level | Who Performs | Focus |
|-------|-------------|-------|
| **Unit** | Developers | Single function/method |
| **Integration** | Developers / Testers | Module interaction |
| **System** | Testers | Entire application |
| **Acceptance** | End Users / QA | Business requirements |

---

## 5. Testing Techniques

### 5.1 Black Box Testing
- Tester has **no knowledge** of internal code
- Tests based on **inputs and expected outputs**
- Examples: Equivalence Partitioning, Boundary Value Analysis

### 5.2 White Box Testing
- Tester has **full knowledge** of the code
- Tests internal logic, branches, paths
- Examples: Statement Coverage, Branch Coverage, Path Testing

### 5.3 Grey Box Testing
- Tester has **partial knowledge** of the code
- Combination of black box and white box
- Used for integration testing

### 5.4 Common Test Design Techniques

| Technique | Description |
|-----------|-------------|
| **Equivalence Partitioning** | Divide inputs into valid/invalid groups |
| **Boundary Value Analysis (BVA)** | Test at the edges of input ranges |
| **Decision Table Testing** | Test combinations of conditions |
| **State Transition Testing** | Test changes in system state |
| **Error Guessing** | Based on tester's experience |

#### Equivalence Partitioning Example
For an age field accepting values `18–60`:
- Valid partition: `18–60` (e.g., test with `30`)
- Invalid partition 1: `< 18` (e.g., test with `10`)
- Invalid partition 2: `> 60` (e.g., test with `70`)

#### Boundary Value Analysis Example
For the same field (`18–60`):
- Test values: `17, 18, 19, 59, 60, 61`

---

## 6. Test Case Writing

A **test case** is a set of conditions used to determine whether a system works correctly.

### Test Case Template

| Field | Description |
|-------|-------------|
| **Test Case ID** | Unique identifier (e.g., TC_001) |
| **Test Title** | Short description of what is being tested |
| **Preconditions** | Setup required before the test |
| **Test Steps** | Step-by-step actions to perform |
| **Test Data** | Input values to use |
| **Expected Result** | What should happen |
| **Actual Result** | What actually happened (filled during execution) |
| **Status** | Pass / Fail / Blocked |
| **Priority** | High / Medium / Low |

### Example Test Case

```
Test Case ID:    TC_LOGIN_001
Title:           Verify successful login with valid credentials
Preconditions:   User is registered; login page is open
Steps:
  1. Enter valid email: user@example.com
  2. Enter valid password: Test@123
  3. Click "Login" button
Expected Result: User is redirected to dashboard
Actual Result:   [To be filled during execution]
Status:          Pass
Priority:        High
```

---

## 7. Bug / Defect Life Cycle

```
New → Assigned → Open → Fixed → Re-test → Closed
                  ↓                ↓
               Deferred         Reopened
```

### Bug Severity vs Priority

| Severity | Priority | Example |
|----------|----------|---------|
| **Critical** | High | App crash on login |
| **Major** | High | Payment not processing |
| **Minor** | Low | Button slightly misaligned |
| **Trivial** | Low | Typo in footer |

> **Severity** = Impact on functionality  
> **Priority** = Urgency of fixing

### Bug Report Template

```
Bug ID:          BUG_001
Title:           Login button unresponsive on mobile
Environment:     iOS 17, Safari, iPhone 14
Steps to Reproduce:
  1. Open app on iPhone
  2. Enter credentials
  3. Tap "Login"
Expected:        User logs in successfully
Actual:          Nothing happens; no response
Severity:        Critical
Priority:        High
Attachments:     [screenshot.png]
```

---

## 8. Software Development & Testing Models

### 8.1 Waterfall Model
- Testing happens **after development** is complete
- Linear and sequential
- Late bug discovery = high cost

### 8.2 V-Model (Verification & Validation)
```
Requirements    ←────────────→  Acceptance Testing
System Design   ←────────────→  System Testing
Architecture    ←────────────→  Integration Testing
Unit Design     ←────────────→  Unit Testing
                   Coding
```
- Each development phase has a corresponding testing phase

### 8.3 Agile Testing
- Testing is **continuous** throughout sprints
- Testers collaborate closely with developers
- Fast feedback loops
- Techniques: TDD, BDD

### 8.4 TDD vs BDD

| | TDD | BDD |
|-|-----|-----|
| **Full Name** | Test-Driven Development | Behavior-Driven Development |
| **Focus** | Code behavior | Business behavior |
| **Written by** | Developers | Developers + QA + Business |
| **Language** | Code (unit tests) | Plain English (Gherkin) |
| **Example tool** | JUnit, pytest | Cucumber, SpecFlow |

#### BDD Example (Gherkin Syntax)
```gherkin
Feature: User Login

  Scenario: Successful login
    Given the user is on the login page
    When they enter valid credentials
    Then they should be redirected to the dashboard
```

---

## 9. Key Testing Concepts

### Test Plan
A document describing the **scope, approach, resources, and schedule** of testing activities.

Key sections:
- Objectives
- Scope (in/out)
- Test strategy
- Entry/Exit criteria
- Test environment
- Risks and mitigations

### Entry & Exit Criteria

| Criteria | Description |
|----------|-------------|
| **Entry** | Conditions to START testing (e.g., build is deployed, requirements are ready) |
| **Exit** | Conditions to STOP testing (e.g., 95% test cases passed, no critical bugs open) |

### Test Coverage
- **Requirement Coverage** – Are all requirements tested?
- **Code Coverage** – What % of code is executed by tests?
  - Statement, Branch, Function, Line coverage

### Exploratory Testing
- **Unscripted** testing where the tester actively explores the application
- Relies on experience and intuition
- Good for finding unexpected bugs

### Regression Testing
- Ensures that **new code changes don't break existing functionality**
- Run after every bug fix or new feature
- Often automated

---

## 10. Common Testing Tools

### Test Management
| Tool | Use |
|------|-----|
| **Jira** | Bug tracking & project management |
| **TestRail** | Test case management |
| **Zephyr** | Test management inside Jira |
| **Xray** | Test management for Jira |

### Automation Testing
| Tool | Language | Use |
|------|----------|-----|
| **Selenium** | Java, Python, C# | Web UI automation |
| **Cypress** | JavaScript | Modern web testing |
| **Playwright** | JS, Python, C# | Cross-browser automation |
| **Appium** | Java, Python | Mobile app testing |
| **pytest** | Python | Unit/integration testing |
| **JUnit** | Java | Unit testing |

### Performance Testing
| Tool | Use |
|------|-----|
| **JMeter** | Load and performance testing |
| **k6** | Modern load testing |
| **Gatling** | High-performance load testing |

### API Testing
| Tool | Use |
|------|-----|
| **Postman** | Manual & automated API testing |
| **REST Assured** | Java-based API test automation |
| **Insomnia** | API client |

### Security Testing
| Tool | Use |
|------|-----|
| **OWASP ZAP** | Web app vulnerability scanning |
| **Burp Suite** | Security testing platform |

---

## 📚 Summary Cheat Sheet

```
Testing Types:     Functional | Non-Functional | Maintenance
Testing Levels:    Unit → Integration → System → Acceptance
Techniques:        Black Box | White Box | Grey Box
Design Methods:    EP | BVA | Decision Table | State Transition
Bug Lifecycle:     New → Assigned → Open → Fixed → Closed
Key Docs:          Test Plan | Test Case | Bug Report
```

---

## 🔗 Further Reading

- [ISTQB Foundation Level Syllabus](https://www.istqb.org/)
- [Agile Testing – Lisa Crispin](https://agiletester.ca/)
- [Software Testing Help](https://www.softwaretestinghelp.com/)
- [Ministry of Testing](https://www.ministryoftesting.com/)

---

*Notes compiled for learning purposes. Feel free to contribute or raise issues!*
