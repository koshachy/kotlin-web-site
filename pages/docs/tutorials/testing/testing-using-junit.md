---
type: doc
layout: tutorial
category: "Testing"
title: "Testing Kotlin using JUnit"
---

# Testing Kotlin using JUnit in JVM

This tutorial shows you how to write a simple test and run it with the Gradle build tool.

The example has the [kotlin.test](/api/latest/kotlin.test/index.html) library under the hood and runs the test using JUnit.

## Adding Dependencies

To start working with kotlin.test and JUnit, add the following dependencies to the Gradle configuration:

<div class="multi-language-sample" data-lang="groovy">
<div class="sample" markdown="1" theme="idea" mode='groovy'>

```groovy
dependencies {
    // Other dependencies.
    // ...
    testImplementation "org.jetbrains.kotlin:kotlin-test:1.3.11"
    testImplementation "org.jetbrains.kotlin:kotlin-test-junit:1.3.11"
}
```

</div>
</div>

<div class="multi-language-sample" data-lang="kotlin">
<div class="sample" markdown="1" theme="idea" mode='kotlin' data-highlight-only>

```kotlin
dependencies {
    // Other dependencies.
    // ...
    testImplementation(kotlin("test"))
    testImplementation(kotlin("test-junit"))
}
```

</div>
</div>

## Creating a Test

Create a new Kotlin file and write the following code:

<div class="sample" markdown="1" theme="idea" data-min-compiler-version="1.3">

```kotlin
class Sample() {

    fun sum(a: Int, b: Int): Int {
        return a + b
    }
}
```
</div>

The `Sample` class contains a function that sums two integers.

To create a test for this code, add a new Kotlin file. It should contain the `Sample` class instance and code for testing its function:

<div class="sample" markdown="1" theme="idea" data-min-compiler-version="1.3">

```kotlin
import kotlin.test.Test
import kotlin.test.assertEquals

internal class SampleTest {

    private val classForTesting: Sample = Sample()

    @Test
    fun testSum() {
        val expected = 42
        assertEquals(expected, classForTesting.sum(40, 2))
    }
}
```
</div>

The test contains the following `kotlin.test` keywords:
- [@Test](/api/latest/kotlin.test/kotlin.test/-test/index.html) annotation. It shows that the testSum function is the test function.
- [assertEquals](/api/latest/kotlin.test/kotlin.test/assert-equals.html) method. It asserts that the expected value is equal to the actual value.

## Running a Test

To run a test via IntelliJ IDEA use the gutter icon to execute it. Also, you can run a test via the command-line interface using the `./gradlew` command. 

