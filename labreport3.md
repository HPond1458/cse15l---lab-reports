# Lab Report 3 - Henry Pond

## Part 1 - Bugs
I chose to analyze the bug in the `filter` method in the ListExamples class. 

### Failure-inducing Test
```
class Check implements StringChecker {
    public boolean checkString(String filter){
        return filter.contains("Test");
    }
}

public class ListTests {
    @Test
    public void testFilterFail() {
        List<String> test = new ArrayList<>();
        test.add("Testing");
        test.add("Not this one");
        test.add("Test me too!");
        List<String> expect = new ArrayList<>();
        expect.add("Testing");
        expect.add("Test me too!");
        Check newCheck = new Check();
        assertEquals(expect,ListExamples.filter(test, newCheck));
    }
}
```

### Successful Test
```
class Check implements StringChecker {
    public boolean checkString(String filter){
        return filter.contains("Test");
    }
}

public class ListTests {
    @Test 
    public void testFilterSuccess() {
        List<String> test = new ArrayList<>();
        test.add("Testing");
        test.add("Not this one");
        test.add("Test me too!");
        test.add("Testing");
        List<String> expect = new ArrayList<>();
        expect.add("Testing");
        expect.add("Test me too!");
        expect.add("Testing");
        Check newCheck = new Check();
        assertEquals(expect,ListExamples.filter(test, newCheck));
    }
}
```

### Test Output
![Test Output](ListTestsOutput.png)

### Fixing The Bug
Before:
```
static List<String> filter(List<String> list, StringChecker sc) {
    List<String> result = new ArrayList<>();
    for(String s: list) {
      if(sc.checkString(s)) {
        result.add(0, s);
      }
    }
    return result;
  }
```

After:
```
static List<String> filter(List<String> list, StringChecker sc) {
    List<String> result = new ArrayList<>();
    for(String s: list) {
      if(sc.checkString(s)) {
        result.add(s);
      }
    }
    return result;
  }
```

### Why It's Fixed
The symptom was that the `filter` method was returning a list of correctly filtered strings in the reverse order of which they appear in the original list.
This is because the method was adding the filtered strings to the beginning of the list instead of the end.
Simply changing `result.add(0, s);` to `result.add(s);` fixes the issue and `filter` will return a list of filtered strings in the order they appear in the original list.

## Part 2 - Researching the `find` Command

