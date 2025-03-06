## 1. Please explain your Automation Framework, all the components.
A test automation framework consists of various components:
- **Page Object Model (POM):** Helps in maintaining object repositories and reducing code duplication.
- **TestNG/JUnit:** Used for test execution and reporting.
- **Maven/Gradle:** Dependency management and build tool.
- **Logging & Reporting:** Log4j, Extent Reports for logging and generating reports.
- **CI/CD Integration:** Jenkins, Azure DevOps for continuous testing.
- **Data Handling:** Using Excel, JSON, or database for test data.
- **Parallel Execution:** Implemented using TestNG or Selenium Grid.

---

## 2. What is a Page Object Model (POM)?
POM is a design pattern that enhances test maintenance and reduces code duplication by separating UI elements from test scripts. Each web page is represented as a class, and elements are stored as variables with reusable methods.

---



## 3. What are the advantages and disadvantages of the Page Object Model?
✅ **Advantages:**
- Code reusability and maintainability.
- Separation of UI elements and test scripts.
- Easier debugging and updates.

❌ **Disadvantages:**
- Increased development time.
- Larger number of classes increases project complexity.

---
