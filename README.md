# Infrastructure Automation Testing Using CI/CD Lab

## Introduction: 

In this lab, you will learn to use an  industry-standard pipeline tool, GitHub Actions, to build a simple CI/CD pipeline for testing.  

## Objective

For this lab, you will gain hands-on experience using GitHub Actions for continuous integration and managing your Jenkins configuration
as code.  You will write pipeline jobs using the Groovy DSL and create a GitHub Actions workflow to Build and Test Java code.

## Getting Started:

1. Copy the starter code from here into a new, private repository in your personal GitHub account. When adding a collaborator, be sure to add the instructor ("CSCC-Instructor").

#### The Gradle Project

The source code for this project is quite simple.  It's a simple Java application and a JUnit test suite.  You won't need to change any of its code.  Note that if you want you can build it from the command line with a simple `./gradlew build`

## Completing the Assignment

### Creating a New Branch
1. At the top of your repo, select the drop down that says "main"
1. In the field that says "Find or create a branch..." type "assignment"

### Creating GitHub Actions Workflow: 

For this lab you will create a GitHub Actions workflow that will execute a pipeline job that will do 3 things:
1. Checkout _your_ repository in a container using the latest version of Ubuntu (Linux)
1. Build the source code using Gradle and upload the executable JAR file to the build summary
1. Report the unit test results by uploading the test report as a zip archive

## Hints
1. Refer to the previous lab which demonstrates how to properly create a Ubuntu container, checkout the code in this repository, then build the Gradle project.
1. To upload the 

## Submitting Your Work

1. Publish your repository as a private repo, and ensure that you have pushed the latest version
1. Open a pull request from your branch to master
1. Submit the assignment in Blackboard 

__NOTE: I will provide feedback via. comments in your pull request.__

## Maven Pipeline Build Snippet
Here is a snippet that will be useful to include in your pipeline.  The "build" stage should include something similar to this: 
```
        withMaven (maven: 'maven3') {
          sh "mvn package"
        }
```
The `withMaven` clause does the necessary setup to make the `mvn` executable that corresponds to the `maven3` tool installation
available to the `sh` command.  Without it the `sh` would complain that it couldn't find `mvn`.
