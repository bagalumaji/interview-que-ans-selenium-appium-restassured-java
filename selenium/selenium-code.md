## 9. Explain the WebDriver create statement line.
Example:
```java
WebDriver driver = new ChromeDriver();
```
- **WebDriver**: Interface reference.
- **ChromeDriver**: Concrete class that launches Chrome.

---


### 6. Write the Code Snippet for Explicit Wait?
```java
WebDriverWait wait = new WebDriverWait(driver, Duration.ofSeconds(10));
WebElement element = wait.until(ExpectedConditions.elementToBeClickable(By.id("submit_button")));
element.click();
```

### 7. Write the Code Snippet for Drag and Drop in Selenium?
```java
Actions action = new Actions(driver);
WebElement source = driver.findElement(By.id("source"));
WebElement target = driver.findElement(By.id("target"));
action.dragAndDrop(source, target).perform();
```

### 8. How do you switch to different Windows in Selenium?
```java
String mainWindow = driver.getWindowHandle();
Set<String> windows = driver.getWindowHandles();
for (String window : windows) {
    if (!window.equals(mainWindow)) {
        driver.switchTo().window(window);
    }
}
```

### 9. Why do we use SET in Window Handles?
**Answer:** A Set ensures unique values (no duplicates) and allows easy iteration over multiple window handles.

### 10. Write the Code for taking a screenshot in Selenium?
```java
File srcFile = ((TakesScreenshot) driver).getScreenshotAs(OutputType.FILE);
FileUtils.copyFile(srcFile, new File("screenshot.png"));
```
