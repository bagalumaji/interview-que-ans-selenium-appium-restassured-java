## 6. What is a Singleton Design Pattern?
A singleton pattern ensures a class has only one instance and provides a global access point. In Selenium, it is used for managing WebDriver instances.

Example:
```java
public class Demo {
    private static Demo demo;

    private Demo() {}

    public static demo getInstance() {
        if (demo == null) {
            demo = new Demo();
        }
        return demo;
    }
}


# Java Solutions for Array and String Problems

## 1. Second Largest Digit in a String
**Problem:** Find the second largest digit in a given string.

### **Solution:**
```java
public static int secondLargestDigit(String s) {
    TreeSet<Integer> digits = new TreeSet<>(Collections.reverseOrder());
    for (char c : s.toCharArray()) {
        if (Character.isDigit(c)) {
            digits.add(c - '0');
        }
    }
    return digits.size() < 2 ? -1 : (int) digits.toArray()[1];
}
```

---

## 2. Count Word Occurrences in a Sentence
**Problem:** Count the occurrences of each word in a given string.

### **Solution:**
```java
public static void countWordOccurrences(String s) {
    String[] words = s.split(" ");
    Map<String, Integer> wordCount = new HashMap<>();
    for (String word : words) {
        wordCount.put(word, wordCount.getOrDefault(word, 0) + 1);
    }
    for (Map.Entry<String, Integer> entry : wordCount.entrySet()) {
        System.out.println(entry.getKey() + " -> " + entry.getValue() + " times");
    }
}
```

---

## 3. Merge Two Arrays
**Problem:** Merge two arrays into a single array.

### **Solution:**
```java
public static int[] mergeArrays(int[] arr1, int[] arr2) {
    int[] merged = new int[arr1.length + arr2.length];
    System.arraycopy(arr1, 0, merged, 0, arr1.length);
    System.arraycopy(arr2, 0, merged, arr1.length, arr2.length);
    return merged;
}
```

---

## 4. Increment a Number Represented as an Array
**Problem:** Increment an array representation of a number.

### **Solution:**
```java
public static int[] incrementArray(int[] arr) {
    int n = arr.length;
    for (int i = n - 1; i >= 0; i--) {
        if (arr[i] < 9) {
            arr[i]++;
            return arr;
        }
        arr[i] = 0;
    }
    int[] newArr = new int[n + 1];
    newArr[0] = 1;
    return newArr;
}
```

---

## 5. Rearrange Array (Even Numbers First, Odd Numbers Last)
**Problem:** Rearrange an array so that all even numbers come first, followed by odd numbers.

### **Solution:**
```java
public static int[] rearrangeArray(int[] arr) {
    Arrays.sort(arr);
    return arr;
}
```

---

## 6. Reverse Each Word in a Sentence
**Problem:** Reverse each word in a sentence while keeping spaces in place.

### **Solution:**
```java
public static String reverseWords(String s) {
    String[] words = s.split(" ");
    StringBuilder result = new StringBuilder();
    for (String word : words) {
        result.append(new StringBuilder(word).reverse()).append(" ");
    }
    return result.toString().trim();
}
```

---

## 7. Main Method for Testing
```java
public static void main(String[] args) {
    System.out.println("Second Largest Digit: " + secondLargestDigit("str1025rts"));
    
    System.out.println("Word Count: ");
    countWordOccurrences("my name is Rohan Rohan");
    
    int[] merged = mergeArrays(new int[]{5, 3, 2}, new int[]{9, 0, 1});
    System.out.println("Merged Arrays: " + Arrays.toString(merged));
    
    System.out.println("Incremented Array: " + Arrays.toString(incrementArray(new int[]{9, 9, 9})));
    
    int[] rearranged = rearrangeArray(new int[]{2, 0, 4, 0, 3, 0, 5, 0});
    System.out.println("Rearranged Array: " + Arrays.toString(rearranged));
    
    System.out.println("Reversed Words: " + reverseWords("abc de f"));
}
```
