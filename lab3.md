Peter Wang. CSE 15L. Lab Report 3.
---

On bugs and commands.

---
**Part 1**

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


**Part 2**

I choose `grep`!

**Number 1**: `ls |grep`

source where I found this use of `grep`: https://en.wikibooks.org/wiki/Grep

Example 1a: Using the command `ls |grep 2210` in the directory `/biomed` helps the user filter many files in a directory by searching for the specified key phrase `2210`. This command lists all the files in `/biomed` that have the characters `2210` in them.
```
peter@Symere MINGW64 ~/OneDrive/Documents/GitHub/docsearch/technical/biomed (main)
$ ls |grep 2210
1471-2210-1-10.txt
1471-2210-1-2.txt
1471-2210-1-3.txt
1471-2210-1-4.txt
1471-2210-1-7.txt
1471-2210-1-8.txt
1471-2210-2-14.txt
1471-2210-2-4.txt
1471-2210-2-5.txt
1471-2210-2-6.txt
1471-2210-2-8.txt
1471-2210-2-9.txt
1471-2210-3-1.txt
1471-2210-3-3.txt
```

Example 1b: Using the command `ls |grep 511X` in the directory `/biomed` helps the user filter many files in a directory by searching for the specified key phrase `511X`. This command lists all the files in `/biomed` that have the characters `511X` in them.
```
peter@Symere MINGW64 ~/OneDrive/Documents/GitHub/docsearch/technical/biomed (main)
$ ls |grep 511X
1476-511X-1-2.txt
1476-511X-2-2.txt
1476-511X-2-3.txt
```

**Number 2**: `ls |grep -v`

source where I found this use of `grep`: https://en.wikibooks.org/wiki/Grep

Example 2a: Using the command `ls |grep -v 13` in the directory `/911report` helps the user filter many files in a directory by excluding a specified key phrase `13`. This command lists all the files in `/911report` that does **not** include `13`.
```
peter@Symere MINGW64 ~/OneDrive/Documents/GitHub/docsearch/technical/911report (main)
$ ls |grep -v 13
chapter-1.txt
chapter-10.txt
chapter-11.txt
chapter-12.txt
chapter-2.txt
chapter-3.txt
chapter-5.txt
chapter-6.txt
chapter-7.txt
chapter-8.txt
chapter-9.txt
preface.txt
```

Example 2b: Using the command `ls |grep -v chapter` in the directory `/911report` helps the user filter many files in a directory by excluding a specified key phrase `chapter`. This command lists all the files in `/911report` that does **not** include `chapter`.
```
peter@Symere MINGW64 ~/OneDrive/Documents/GitHub/docsearch/technical/911report (main)
$ ls |grep -v chapter
preface.txt
```

**Number 3**: `ls |grep -e`

source where I found this use of `grep`: https://en.wikibooks.org/wiki/Grep

Example 3a: Using the command `ls |grep -e txt` in the directory `/911report` helps the user filter and sort many files in a directory by including a specified key phrase `txt`. This command lists all the files in `/911report` with the character `txt` and sorts them in alphabetical and numerical order.
```
peter@Symere MINGW64 ~/OneDrive/Documents/GitHub/docsearch/technical/911report (main)
$ ls |grep -e txt
chapter-1.txt
chapter-10.txt
chapter-11.txt
chapter-12.txt
chapter-13.1.txt
chapter-13.2.txt
chapter-13.3.txt
chapter-13.4.txt
chapter-13.5.txt
chapter-2.txt
chapter-3.txt
chapter-5.txt
chapter-6.txt
chapter-7.txt
chapter-8.txt
chapter-9.txt
preface.txt
```
Example 3b: Using the command `ls |grep -e 1` in the directory `/911report` helps the user filter and sort many files in a directory by including a specified key phrase `1`. This command lists all the files in `/911report` with the character `1` and sorts them in alphabetical and numerical order.
```
peter@Symere MINGW64 ~/OneDrive/Documents/GitHub/docsearch/technical/911report (main)
$ ls |grep -e 1
chapter-1.txt
chapter-10.txt
chapter-11.txt
chapter-12.txt
chapter-13.1.txt
chapter-13.2.txt
chapter-13.3.txt
chapter-13.4.txt
chapter-13.5.txt
```
**Number 4**: `ls |grep -n`

source where I found this use of `grep`: https://en.wikibooks.org/wiki/Grep

Example 4a: Using the command `ls |grep -n chapter` in the directory `/911report` helps the user filter and number many files in a directory by including a specified key phrase 'chapter'. This command lists all the files in `/911report` with the characters `chapter` and numbers them according to how they would be numbered from a numerical and alphabetical sort. This also means that it can also be useful for finding out how many files there are that meet the filter. In this case, there are 16 files with `chapter` in them.
```
peter@Symere MINGW64 ~/OneDrive/Documents/GitHub/docsearch/technical/911report (main)
$ ls |grep -n chapter
1:chapter-1.txt
2:chapter-10.txt
3:chapter-11.txt
4:chapter-12.txt
5:chapter-13.1.txt
6:chapter-13.2.txt
7:chapter-13.3.txt
8:chapter-13.4.txt
9:chapter-13.5.txt
10:chapter-2.txt
11:chapter-3.txt
12:chapter-5.txt
13:chapter-6.txt
14:chapter-7.txt
15:chapter-8.txt
16:chapter-9.txt
```

Example 4b: Using the command `ls |grep -n 13` in the directory `/911report` helps the user filter and number many files in a directory by including a specified key phrase '13'. This command lists all the files in `/911report` with the characters `13` and numbers them according to how they would be numbered from a numerical and alphabetical sort. This also means that it can also be useful for finding out how many files there are that meet the filter. In this case, there are 5 files with `13` in them.
```
peter@Symere MINGW64 ~/OneDrive/Documents/GitHub/docsearch/technical/911report (main)
$ ls |grep -n 13
5:chapter-13.1.txt
6:chapter-13.2.txt
7:chapter-13.3.txt
8:chapter-13.4.txt
9:chapter-13.5.txt
```
