# Selenium Automation Interview Questions & Answers


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


