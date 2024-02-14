Peter Wang. CSE 15L. Lab Report 3.
---

Bugs and Commands.

---
Part 1
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
