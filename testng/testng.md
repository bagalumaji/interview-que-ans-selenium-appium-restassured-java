
## **TestNG**

### 11. How do you run the failed test cases?
Use TestNG’s **retryAnalyzer** or execute failed test cases from `testng-failed.xml`.

---

### 1. What are the different annotations used in TestNG?
**Answer:**
- `@BeforeSuite`, `@AfterSuite`
- `@BeforeTest`, `@AfterTest`
- `@BeforeClass`, `@AfterClass`
- `@BeforeMethod`, `@AfterMethod`
- `@Test`

### 2. Write the hierarchy of annotations in TestNG?
**Answer:**
```
@BeforeSuite → @BeforeTest → @BeforeClass → @BeforeMethod → @Test → @AfterMethod → @AfterClass → @AfterTest → @AfterSuite
```

### 3. How do you run the failed test cases?
**Answer:** Use `testng-failed.xml` generated after execution or implement `retryAnalyzer` in TestNG.

### 4. How do you decide the priorities of your Test Cases?
**Answer:** Using `priority` attribute in `@Test` annotation.
```java
@Test(priority = 1)
public void testLogin() {}
@Test(priority = 2)
public void testDashboard() {}
```

### 5. If you want to execute one test case again and again how do you do that?
**Answer:** Using `invocationCount` in `@Test`.
```java
@Test(invocationCount = 5)
public void repeatTest() {}
```
