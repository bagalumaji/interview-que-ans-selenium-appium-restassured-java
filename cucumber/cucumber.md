# Selenium Automation Interview Questions & Answers

## 1. Please introduce yourself.
A strong introduction should include your total experience, key skills, current role, and notable projects. Example:

> *"I am Umaji Bagal, a Senior Test Engineer with over 7 years of experience in automation and manual testing. I have expertise in Selenium with Java and C#, API testing using Rest Assured and Postman, mobile automation using Appium, and framework development using Playwright. I have worked in Agile and DevOps environments, contributing to test automation frameworks, CI/CD integration, and test execution across multiple platforms."*

---

## 4. How do you run your test cases in parallel in Cucumber?
Parallel execution in Cucumber can be achieved using:
- **TestNG with Cucumber:** Define `<suite>` in `testng.xml`.
- **Cucumber-JUnit with Maven Surefire Plugin:** Add the parallel execution setting in `pom.xml`.
- **Cucumber with JVM Parallel Plugin:** Uses `@RunWith(ParallelCucumber.class)`.

---

## 5. Explain the contents of the Runner File in Cucumber.
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


