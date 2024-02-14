Peter Wang. CSE 15L. Lab Report 3.
---

Bugs and Commands.

---
Part 1

One of the bugs in week 4's lab was in the `reverseInPlace` method in `ArrayExamples.java`. I chose this one.

A failure-inducing input for the buggy `reverseInPlace` method would be:
```
@Test 
public void testReverseInPlace() {
    int[] input2 = {4, 5, 6};
    ArrayExamples.reverseInPlace(input2);
    assertArrayEquals(new int[]{6, 5, 4}, input2);
}
```

An input that doesn't induce a failure, yet still uses the same buggy `reverseInPlace` method would be:
```
@Test
public void testReverseInPlace2() {
    int[] input1 = {3};
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{3}, input1);
}
```

Here is the symptom of running the two inputs as tests using JUnit. `testReverseInPlace2()` passes, `testReverseInPlace()` doesn't.
![image](https://github.com/petruswagnavian/cse15l-lab-reports/assets/141669683/dea869cc-5fd5-4f96-86a7-261833dcd422)


Before the fix, the bug exists in the code of the method `reverseInPlace`.
```
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
}
```



