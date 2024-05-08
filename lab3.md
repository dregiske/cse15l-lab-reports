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

1. ```grep -c``` on files:

```
Andres-MacBook-Air:docsearch-main AndreGiske$ grep -c "is" ./technical/biomed/1471-2253-2-5.txt
272
```
The output is a number because ```-c``` counts how many lines contain the pattern in a given file. In this case, 272 lines in the file ```1471-2253-2-5.txt``` have the word "is" somewhere in it.

2. ```grep -c``` on directories:

```
Andres-MacBook-Air:docsearch-main AndreGiske$ grep -c "is" ./technical/biomed/
grep: ./technical/biomed/: Is a directory
```
The command ```grep -c``` does not work on directories because they don't hold text and words like files do.

3. ```grep -l``` on files:

```
Andres-MacBook-Air:docsearch-main AndreGiske$ grep -l "permission" ./technical/biomed/*.txt
./technical/biomed/1471-2199-3-12.txt
./technical/biomed/1471-2199-4-4.txt
./technical/biomed/1471-2407-2-17.txt
./technical/biomed/1471-2431-3-5.txt
./technical/biomed/1471-2458-3-2.txt
./technical/biomed/1472-684X-1-5.txt
./technical/biomed/1472-6947-2-4.txt
./technical/biomed/1477-7525-1-10.txt
./technical/biomed/ar750.txt
```
The output is a list of different file names because the command ```grep -l``` returns all the file names that contain the given pattern. In this case all the ```.txt``` files listed in the output all contain the word "permission" in them.

4. ```grep -l``` on directories:

```
Andres-MacBook-Air:docsearch-main AndreGiske$ grep -l "permission" ./technical/biomed/
grep: ./technical/biomed/: Is a directory
```
The command ```grep -l``` does not work on directories that is why it returns an error.


5. ```grep -i``` on files:

```
Andres-MacBook-Air:docsearch-main AndreGiske$ grep -i "five" ./technical/government/Media/5_Legal_G
roups.txt
Five independent Salt Lake organizations that provide legal
Community Legal Center hosted by staff members of the five
building and not paying rent times five will save the non-profit
```
The output returns any sentence that contains the pattern. This command is insensitive so it will match the pattern with the same word no matter the capitalization. In this case, it returned 3 sentences from the file, ```5_Legal_Groups.txt``` that all contain the word five, even Five was counted as a match.

6. ```grep -i``` on directories:

```
Andres-MacBook-Air:docsearch-main AndreGiske$ grep -i "five" ./technical/government/Media/
grep: ./technical/government/Media/: Is a directory
```
The command ```grep -i``` does not work on directories that is why it returned an error statement.

7. ```grep -w``` on files:

```
Andres-MacBook-Air:docsearch-main AndreGiske$ grep -w "five" ./technical/government/Media/5_Legal_G
roups.txt
Community Legal Center hosted by staff members of the five
building and not paying rent times five will save the non-profit
```
The output returns an sentence that has a perfect match of the pattern. Unlikes ```grep -i```, ```-w``` is sensitive so it will match only directly equivalent words, capitalization matters. The output is only 2 sentences now that contain the pattern "five" from the file ```5_Legal_Groups.txt```.

8. ```grep -w``` on directories:

```
Andres-MacBook-Air:docsearch-main AndreGiske$ grep -w "five" ./technical/government/Media/
grep: ./technical/government/Media/: Is a directory
```
The command ```grep -w``` does not work on directories which is why it returns an error statement.
