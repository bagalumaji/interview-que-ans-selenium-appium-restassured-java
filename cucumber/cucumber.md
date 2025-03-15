## **Cucumber**

## 1. How do you run your test cases in parallel in Cucumber?
Parallel execution in Cucumber can be achieved using:
- **TestNG with Cucumber:** Define `<suite>` in `testng.xml`.
- **Cucumber-JUnit with Maven Surefire Plugin:** Add the parallel execution setting in `pom.xml`.
- **Cucumber with JVM Parallel Plugin:** Uses `@RunWith(ParallelCucumber.class)`.

---

## 2. Explain the contents of the Runner File in Cucumber.
A Cucumber Runner file includes:
- `@RunWith(Cucumber.class)`: Specifies the test runner.
- `@CucumberOptions`: Includes `features` (path to feature files), `glue` (step definitions), `plugin` (reports), `dryRun`, and `tags` for filtering scenarios.

Example:
```java
@RunWith(Cucumber.class)
@CucumberOptions(
    features = "src/test/resources/features",
    glue = "stepDefinitions",
    plugin = {"pretty", "html:target/cucumber-reports"},
    monochrome = true
)
public class TestRunner {}
```

---

### 1. How do you run your test cases in parallel in Cucumber?
**Answer:** By configuring `cucumber-jvm-parallel-plugin` in `pom.xml`.

### 2. Explain the contents of the Runner File in Cucumber?
**Answer:**
```java
@RunWith(Cucumber.class)
@CucumberOptions(features = "src/test/resources/features", glue = "stepDefinitions")
public class TestRunner {}
```
- `features`: Path of feature files.
- `glue`: Package containing step definitions.

### 3. What is the difference between Scenario and Scenario Outline in Cucumber?
**Answer:**
- **Scenario**: Executes a single example.
- **Scenario Outline**: Uses `Examples` to run the same scenario with multiple datasets.

### 4. How do you pass data to your Selenium Scripts?
**Answer:** Using DataTables or Examples in Cucumber.
