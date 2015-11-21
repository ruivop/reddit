#Software Testing

#Introduction
First of, reddit was created by a group of students to be used as an online bulletin board system. At first, the company was only a startup and reddit was supposed to be an app for ordering food. After the stakeholders (Y Combinator) received the idea, they gave their input on the subject, and reddit was created. It started with only 2 students, and no one expected it to be what it was today.

##How testable is reddit?

##How to improve its testability?
It can be improved by test-driven development and design for testability.
##CUT (Component Under Test): the component being tested

#FIRST
##Controllability: How possible is to control the state of the CUT as required for testing
##Observability: How possible is to observe intermediate and final test results.
##Isolateability: How much CUT can be tested in isolation-
##Separation of concerns: How much every test is separated. i.e. are they all on the same test? are they well separated.
##Understandability: How well is CUT documented and easy to understand.
##Heterogeneity: How many techonologies are required to run all the test methods and tools.


#Software Testing

##Unit Testing

##Functional Testing
Functional testing is a type of Black Box Testing () whose tests are based on the specifications of the software CUT. They accept different inputs and then the output is examined, leaving the structure of the program out of the equation. This type of test only shows what the software is doing.

Even though reddit contains a folder with the functional tests, there's only a file init.py, with 20 lines and it's mostly a license.

##Integration Testing

##Component Interface Testing

##System Testing

##Acceptance Testing

##Compatibility Testing

##Regression Testing

##Software Performance Testing

##Accessibility Testing

##Security Testing


#Validation & Verification


#Coverage of tests (EclEmma, others)


#Bug

##Bug Report

##Test Cases

##Automated software fault diagnosis