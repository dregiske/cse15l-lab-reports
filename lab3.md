PART 1

1. A failure-inducing input for the buggy program:

```
public class ArrayTests {
  @Test
  public void failureInducingTest(){
    int[] input1 = {1, 2, 3};
    ArrayExamples.reversed(input1);
    assertArrayEquals(new int[]{3, 2, 1}, ArrayExamples.reversed(input1));
  }
}
```

2. An input that doesn't induce a failure:

```
public class ArrayTests {
  @Test
  public void nonFailureInducingTest(){
    int[] input1 = {0};
    ArrayExamples.reversed(input1);
    assertArrayEquals(new int[]{0}, ArrayExamples.reversed(input1));
  }
}
```

3. The symptom, as the output of running the two tests above:
![Screen Shot 2024-05-06 at 8 06 52 PM](https://github.com/dregiske/cse15l-lab-reports/assets/146780188/9691da68-e614-40f6-82bd-054c23929c58)

4. The bug, as the before-and-after:

Before
```
public class ArrayExamples {
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
}
```
After
```
public class ArrayExamples {
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArray[i] = arr[arr.length - i - 1];
    }
    return newArray;
  }
}
```

5. Why the fix addresses the issue:

Before the ```reversed``` method was changed, it iterates through array ```arr``` and then at the end replaces the elements of ```arr``` with the elements of array ```newArray```. However, ```newArray``` is still an empty array so it replaces ```arr``` elements with ```0```. So by changing the bottom lines of code to replace the elements of ```newArray``` instead of ```arr``` it runs the method properly.

PART 2

grep -c on files:
```
Andres-MacBook-Air:docsearch-main AndreGiske$ grep -c "is" ./technical/biomed/1471-2253-2-5.txt
272
```
The output is 272 because -c counts how many lines contain the pattern in a given file. In this case, 272 lines in the file ```1471-2253-2-5.txt``` have the word "is" somewhere in it.

grep -c on directories:
```
Andres-MacBook-Air:docsearch-main AndreGiske$ grep -c "is" ./technical/biomed/
grep: ./technical/biomed/: Is a directory
```
The command ```grep -c``` does not work on directories because they don't hold text and words like files do.

```grep -l /Desktop```

```grep -i "word" text1.txt``` insensitive - will match to the pattern no matter the capitalization

```grep -w "word" text1.txt``` sensitive - will match only directly equivalent words
