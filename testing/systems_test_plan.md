# Systems Test Plan - Liquid Investigations Q4

## References
  - Website - https://liquidinvestigations.org
  - Wiki - https://github.com/liquidinvestigations/liquidinvestigations/wiki
  - Architecture Document - https://github.com/liquidinvestigations/liquidinvestigations/wiki/Architecture-Documentation
  - API Documentation - https://liquidinvestigations.docs.apiary.io/#
  - Milestones Document @Andreea : should we publish this somewhere
  - Narrative Reports @Andreea: should we publish these somewhere
  - Waffle - https://waffle.io/liquidinvestigations/liquidinvestigations
  - Jenkins build system: https://jenkins.liquiddemo.org/


## Introduction
  This plan outlines the systems testing work to be completed by the Liquid Investigations team to meet its Q4 milestone requirements (Jan. 31).
  This plan is a companion of the User Testing Plan, @Andreea to add UAT plan link here.

  The testing work described in this plan will be completed by the whole of the technical team, with automated testing a priority of the implementation team.

  This testing phase will begin on December 1st, 2017, and complete in mid-January.

## Test Items
All tests (manual and automated) are to be performed against the following configurations:
  - x86 (Cloud-based)
    - Will run in a virtual machine
  - x86 (NUC)
    - @Andreea please let me know what NUCs we have, where they are?
  - ARM (ODroid C2)
    - @Alex / @Gabi please let me know if there's another target ARM architecture that awe want to test for.

The images tested will all be built by the Jenkins build system. All test failures will be trackable back to a given build number in Jenkins. No formal testing will take place against ad-hoc or manual builds.


## Software Risk Issues

  - Performance of indexing/search may lead to an intolerably slow product, particularly on the ARM architecture.
  - ARM boards may crash if used with
    - More than x VPN clients
    - More than x Hoover clients
    - More than x MB of indexed Hoover data
  - Discovery may not function properly over VPN
  - VPN users may not be able to access each other's boards
  - In general, the milestone definition document is vague in its definition of requirements. We have historically used this to our advantage, but it is important that we pay close attention that we don't interpret away any important test items.
  - @Alex / @Gabi / @Andreea can you please add to this list with any risks that you've identified?
    - starting points:
      - what worries you most?
      - in past testing, what caused the most problems?


## Scope

### Features to be Tested

  - Discovery
  - Single Sign-On / OAuth2
  - Drag & Drop Indexing
  - VPN
  - User Management
  - API endpoints
    - https://liquidinvestigations.docs.apiary.io/#
    - TODO : @Alex/@Gabi is apiary.io complete and up to date?
  - UI elements
    - First-config Wizard
    - Admin Panel
    - Front Page
    - Per-application Login Screens (from Facelift (http://sentre.de:6080/grain/pbnGyBP7g4Nk4eGcKPtttJ) #TODO: update with proper public link when this document is complete)

### Features not to be Tested

Individual application features will not be tested as part of this plan, this includes:

  - Search (Hoover)
  - Chat (Matrix)
  - File Sharing (Davros)
  - Annotation (Hypothesis)
  - Wiki (Dokuwiki)

Testing of applications and application interoperability will be covered in the User Acceptance Testing plan. @Andreea to provide a link to this

## Approach

Automated functional test plans and test suites are to be written for the following components:
  - Discovery
  - VPN
  - User Management
  - All other API endpoints
    - https://liquidinvestigations.docs.apiary.io/#
    - @Alex / @Gabi is apiary.io complete and up to date?

Automated performance test plans and test suites are to be written for the following components:
 - VPN (scalability/stress testing)
 - Hoover Indexing (scalability/stress testing)

Manual test plans and test suites are to be written for the following components
  - Single Sign-On (today)/OAuth2 (Q4)
  - Drag & Drop Indexing
  - UI elements
    - First-config Wizard
    - Admin Panel
    - Front Page
    - Per-application Login Screens (from Facelift (http://sentre.de:6080/grain/pbnGyBP7g4Nk4eGcKPtttJ) #TODO: update with proper public link to facelift requirements when this document is complete)

Test planning and test suite writing will be completed before the end of November, with testing to begin at the beginning of December.

## Item Pass/Fail Criteria

We will consider an item to have 'passed' if its associated tests have a 100% passing rate.


## Suspension Criteria/Resumption Requirements

In case of build failures, all testing activities will be suspended while team efforts are focused on fixing the build process. Testing will resume once builds are running smoothly

In case of smoke test failures, all testing activities will be suspended while team efforts are focused on fixing the problems uncovered by the smoke test. Testing will resume once smoke tests are passing.

In case of a high number (>50%) of tests failing, testing may be suspended until the tech team has confidence that the system is in a more stable state.

In case of basic functionality (ie. login) not working, testing will be suspended until the tech team has fixed the problem.


## Test Deliverables

For each feature to be tested the following will be produced:

  - Test Plan Documents
  - Test Suites
    - For manual tests, these can be a google sheet with columns for:
      - test
      - expected result
      - actual result
      - pass/fail
    - For automated and performance tests, these should be a well documented set of tests (preferably written in python). Docstrings should be used to describe the test actions and expected outcomes.


  - Test Result Reports
    - For manual tests, these can be a dated google sheet outlining the actual test results an a percentage of test successes
    - For automated tests this


## Remaining Test Tasks
  - As described in 'Features not to be Tested' above, all User Acceptance Testing (primarily application functionality testing) is to be completed under the User Acceptance Testing plan, not this one. @Andreea to link to her plan.

## Environmental/Hardware needs
  - @Nathan will need some ARM boards.
  - @Nathan may need a NUC.
  - NOTE: a large number of the existing ARM boards are currently being used as build slaves/automated test runners. It may not be appropriate to use them for any other testing, and so we might need to buy more
  - @Gabi / @Alex Please provide input here -- what do we have today that is not tied up with Jenkins work? @Andreea -- do you know what we have in Leipzig right now?

## Staffing and Training Needs

We are constrained by resources and budget, and so the bulk of the testing work should be completed by the existing team. Boris has said that he may be available to help us this quarter, and it may also be possible to temporarily hire one or two manual testers to assist us.

As we would like to begin testing for December 1st, it is important that all team members be involved in the test plan and test suite writing process.

Details of work assignments will be discussed with @Andreea and the team this week. (Nov 6.)
