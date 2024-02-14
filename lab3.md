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


Before the fix, the bug exists in the code of the method `reverseInPlace`:
```
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
}
```
After the fix, the code is changed to look like this:
```
static void reverseInPlace(int[] arr) {
    int[] temp = new int[arr.length];
    for(int i = 0; i < arr.length; i++) {
      temp[i] = arr[i];
    }
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = temp[arr.length - i - 1];
    }
}
```
The issue was that the line `arr[i] = arr[arr.length - i - 1];` is updating the list `arr` while also using the same list as a template to access the elements to replace. So, if the input array was `{4, 5, 6}` then the first iteration would update the first element to make the list {6, 5, 6}, and then the third iteration would not be able to update the third element from `6` to `4` correctly because the `4` is not preserved.

This issue is fixed after the code change because a template array is created to store the original elements of the `arr` list. So, the line `arr[i] = temp[arr.length - i - 1];` would be able to update each element in `arr` correctly, and no elements are replaced when they are still needed in a later iteration.


