

## 8. What is Selenium Grid?
Selenium Grid allows parallel test execution across multiple machines, browsers, and environments.

---

## 12. How do you generate Reports in Selenium?
- **Extent Reports:** Provides detailed HTML reports.
- **TestNG Reports:** Default reporting framework.
- **Allure Reports:** Advanced reporting.

---


## 13. How do you customize reports after test execution?
By integrating **Extent Reports** with custom log levels and screenshots.

---


## 14. What kinds of waits are there in Selenium?
- **Implicit Wait**: Applies globally.
- **Explicit Wait**: Waits for a specific condition.
- **Fluent Wait**: Custom polling intervals.

---

## 15. Write the Code Snippet for Explicit Wait.
```java
WebDriverWait wait = new WebDriverWait(driver, Duration.ofSeconds(10));
WebElement element = wait.until(ExpectedConditions.visibilityOfElementLocated(By.id("example")));
```

---

## 16. Write the Code Snippet for Drag and Drop in Selenium.
```java
Actions actions = new Actions(driver);
actions.dragAndDrop(sourceElement, targetElement).build().perform();
```

---


## 17. How do you switch to different Windows in Selenium?
```java
for (String windowHandle : driver.getWindowHandles()) {
    driver.switchTo().window(windowHandle);
}
```

---

## 18. Why do we use SET in Window Handles?
`Set<String>` ensures unique window handles and avoids duplicates.

---

## 19. Write the Code for Taking Screenshot in Selenium.
```java
File src = ((TakesScreenshot) driver).getScreenshotAs(OutputType.FILE);
FileUtils.copyFile(src, new File("screenshot.png"));
```

---


## 20. Difference between Scenario and Scenario Outline in Cucumber?
- `Scenario`: Runs once.
- `Scenario Outline`: Uses Examples for multiple test data.



# Selenium Interview Questions and Answers

## 1. Explain Selenium 4 version architecture?
Selenium 4 introduces the W3C WebDriver standard, eliminating the JSON Wire Protocol used in Selenium 3. It communicates directly with the browser drivers, reducing overhead and improving stability.

## 2. What is the difference between Selenium 3 and Selenium 4 architecture?
- **Selenium 3:** Uses the JSON Wire Protocol to communicate between WebDriver and browser drivers.
- **Selenium 4:** Uses W3C WebDriver Protocol for direct communication, reducing latency and increasing efficiency.

## 3. What are the new features added in Selenium 4?
- Relative Locators
- Improved Window and Tab Management
- Full Page Screenshot Capability
- Enhanced Selenium Grid
- Improved Documentation and Better Observability

## 4. How to switch frames if a frame doesn't have name or ID?
Use the WebElement approach:
```java
WebElement frameElement = driver.findElement(By.xpath("//iframe"));
driver.switchTo().frame(frameElement);
```

## 5. What are the Selenium Components?
- Selenium WebDriver
- Selenium IDE
- Selenium Grid

## 6. What is the use of Selenium Grid and have you used it in your project?
Selenium Grid allows parallel execution across multiple browsers and machines. It is used for distributed testing to save execution time.

## 7. Difference between Assert and Verify?
- **Assert:** Stops execution if the condition fails.
- **Verify:** Continues execution even if the condition fails.

## 8. How do you handle StaleElementReferenceException?
- Use `Thread.sleep()` for short waits.
- Implement `WebDriverWait`.
- Refresh the page before interacting with the element again.

## 9. How do you handle dynamic elements in Selenium?
Use XPath with `contains()`, `starts-with()`, or `normalize-space()`.
```java
driver.findElement(By.xpath("//button[contains(text(),'Login')]")).click();
```

## 10. How do you scroll up and down in Selenium?
```java
JavascriptExecutor js = (JavascriptExecutor) driver;
js.executeScript("window.scrollBy(0,500)"); // Scroll Down
js.executeScript("window.scrollBy(0,-500)"); // Scroll Up
```

## 11. How do you enter text in an input box without using sendKeys()?
```java
JavascriptExecutor js = (JavascriptExecutor) driver;
js.executeScript("document.getElementById('textbox').value='Test'");
```

## 12. How do you find broken links in a webpage using Selenium?
```java
HttpURLConnection connection = (HttpURLConnection) new URL(linkURL).openConnection();
connection.connect();
int responseCode = connection.getResponseCode();
if (responseCode >= 400) {
    System.out.println("Broken Link: " + linkURL);
}
```

## 13. Write XPath to find elements where amount is greater than 600.
```java
//td[text()>600]
```

## 14. What is the use of DesiredCapabilities in Selenium?
It helps to configure browser properties before execution.

## 15. How do you select the 4th radio button in a web table?
```java
driver.findElements(By.xpath("//input[@type='radio']")).get(3).click();
```

## 16. What is your role in Automation Testing?
- Writing test scripts
- Framework maintenance
- Test execution
- CI/CD integration

## 17. How do you upload a file in Selenium?
```java
WebElement upload = driver.findElement(By.id("fileUpload"));
upload.sendKeys("C:\\path\\to\\file.txt");
```

## 18. How to take a full-page screenshot in Selenium?
```java
File screenshot = ((TakesScreenshot) driver).getScreenshotAs(OutputType.FILE);
FileUtils.copyFile(screenshot, new File("fullpage.png"));
```

## 19. How to highlight an element in Selenium?
```java
JavascriptExecutor js = (JavascriptExecutor) driver;
js.executeScript("arguments[0].style.border='3px solid red'", element);
```

## 20. What are the Listeners available in Selenium?
- ITestListener
- WebDriverEventListener

## 21. What OOPS concepts are used in Selenium?
- Encapsulation
- Inheritance
- Polymorphism
- Abstraction

## 22. What Java collections concepts are used in Selenium?
- List, Set, Map
- Queue (for parallel execution management)

## 23. Explain the Selenium framework used in your project.
It typically includes:
- TestNG or JUnit
- Page Object Model (POM)
- Data-driven, Keyword-driven, Hybrid Framework

## 24. How to select the last option in a dropdown?
```java
Select dropdown = new Select(driver.findElement(By.id("dropdown")));
List<WebElement> options = dropdown.getOptions();
dropdown.selectByIndex(options.size() - 1);
```

## 25. Difference between findElement and findElements?
- **findElement:** Returns a single WebElement or throws NoSuchElementException.
- **findElements:** Returns a List of WebElements.

## 26. What are the return types for findElement and findElements?
- **findElement:** WebElement
- **findElements:** List<WebElement>

## 27. What is the return type of getWindowHandle() and getWindowHandles()?
- `getWindowHandle()`: String
- `getWindowHandles()`: Set<String>

## 28. Difference between driver.close() and driver.quit()?
- **close():** Closes the current browser window.
- **quit():** Closes all opened browser windows.

## 29. Difference between build() and perform() in Selenium?
- **build():** Creates an Action sequence but does not execute it.
- **perform():** Executes the Action sequence.

## 30. How do you handle frames in Selenium?
```java
driver.switchTo().frame("frameName");
```

## 31. Where can we use sendKeys other than findElement()?
- Alert boxes
- File Upload dialogs

## 32. Which version of Selenium is used in your framework?
Provide the specific Selenium version from `pom.xml` or dependencies.

## 33. Difference between WebDriver and RemoteWebDriver?
- **WebDriver:** Local browser automation.
- **RemoteWebDriver:** Used for remote execution (Selenium Grid).

## 34. Can we use Selenium methods without exceptions?
No, handling exceptions is necessary to avoid script failures.

## 35. How to take a screenshot in Selenium?
```java
File srcFile = ((TakesScreenshot) driver).getScreenshotAs(OutputType.FILE);
FileUtils.copyFile(srcFile, new File("screenshot.png"));
```

## 36. How to provide default wait time for the entire project in Selenium?
Use implicit waits:
```java
driver.manage().timeouts().implicitlyWait(10, TimeUnit.SECONDS);
```

## 37. Write a Unique XPath to find the first 4 links in a Webpage.
```java
//a[position()<=4]
```

This Markdown file provides answers to frequently asked Selenium interview questions with Java code examples. 🚀


