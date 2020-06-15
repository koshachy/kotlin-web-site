---
type: doc
layout: reference
category: "Testing"
title: "Testing Overview"
---

# Testing in Kotlin Overview

This section covers basic unit test concepts in Kotlin.

> A unit test is a common concept for most programming languages, so if you're familiar with it, you can skip this introduction and proceed to [the tutorials](../tutorials/testing/testing-using-junit.html).
{:.note}

## Unit Testing Basics

Unit tests allow comparing the actual result with the expected. You divide the functionality of your code into discrete units and test them separately.

A unit test requires the framework to write a test, and a test runner engine to launch it. Various frameworks provide their APIs to write tests: [JUnit](https://junit.org/junit5/), [Kotest](https://github.com/kotest/kotest), [TestNG](https://testng.org/doc/).

The [kotlin.test](/api/latest/kotlin.test/index.html) library provides annotations and asserting functions to unify test code.
It allows writing tests independently of the test framework.

## Organizing and Running Test Code

Units test are independent parts of the code and should be placed separately.

Usually, tests are launched using the build tool. For example, Gradle.

Running tests in a Gradle build is supported by default for JVM, Android, Linux, Windows, and macOS.
You need to configure JS and other Kotlin/Native targets manually to run the tests with an appropriate environment, an emulator, or a test framework.

See the following articles for details:
- [Running test in multiplatform projects](building-mpp-with-gradle.html#running-tests).
- [Running test in JS](../tutorials/javascript/running-tests.html).
- [Running test in JVM using JUnit](../tutorials/testing/testing-using-junit.html).
