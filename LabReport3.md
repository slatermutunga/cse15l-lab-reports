# Lab Report 3

## Failure Inducing Input

```
  public void testReverseInPlace() {
    int[] input1 = {1, 2, 3};
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 3, 2, 1 }, input1);
	}
```

## Non Failure Inducing Input

```
    public void testReverseInPlace() {
      int[] input1 = {1, 2, 1};
      ArrayExamples.reverseInPlace(input1);
      assertArrayEquals(new int[]{ 1, 2, 1 }, input1);
  	}
```

## Symptom JUnit Tests

## Test 1

![Image](JUnitBug.png)

## Test 2 
![Image](JunitWorks.png)

## Fixing Bug

## Original Code

```
    static void reverseInPlace(int[] arr) {
    	for(int i = 0; i < arr.length; i += 1) {
         	arr[i] = arr[arr.length - i - 1];
        }
    }
```

## Fixed Code
```
 static void reverseInPlace(int[] arr) {
    int l = arr.length;
    int[] reversedArray = new int[l];
    for(int i = 0; i < arr.length; i += 1) {
	     reversedArray[i] = arr[l - i - 1];
    }
    
    for(int i = 0; i < arr.length; i++){
             arr[i] = reversedArray[i];
    }
}
```

This fixes the issue as initialiy it doesn't use two arrays. This is neccessary because in the original code it would rewrite the values in arr[i] before getting to read ones needed. For example 
arr[0] would get changed to hold arr[2] in the first run of the for loop. Then when you want to put arr[0] into arr[2] its the wrong value. By changing it so there is another array you can use it to hold
all of the values in arr in reversed order, and then use another for loop to put the reversed values into arr, in the correct order.

# Researching the Find Command

## -name

```
slatermutunga@Slaters-MacBook-Pro docsearch % find technical/ -name "911report"
technical//911report
```

This searches the directory technical and finds all of the files or directorys that are called 911report. This gave us the output which showed how there is a directory called 911report.

```
slatermutunga@Slaters-MacBook-Pro docsearch % find technical/ -name "chapter-8.txt"
technical//911report/chapter-8.txt
```

This searches the directory technical and finds all of the files or directorys that are called   
chapter-8.txt. This gave us the output that shows that there is a file called chapter-8.txt in the directory 911report.

I used this option in the lab but I also came across it while researching other options for the find command in the [Linux manual page](https://man7.org/linux/man-pages/man1/find.1.html).

## -type

```
slatermutunga@Slaters-MacBook-Pro docsearch % find technical/ -type d
technical/
technical//government
technical//government/About_LSC
technical//government/Env_Prot_Agen
technical//government/Alcohol_Problems
technical//government/Gen_Account_Office
technical//government/Post_Rate_Comm
technical//government/Media
technical//plos
technical//biomed
technical//911report
```

This searches the directory technical for all of type, d, which is all of the directories. This gave us the output which showed us all of the main directories and also the ones inside of those.

```
slatermutunga@Slaters-MacBook-Pro docsearch % find technical type -f
technical//biomed/gb-2002-3-10-research0055.txt
technical//biomed/1471-2121-2-3.txt
technical//biomed/1471-213X-1-11.txt
technical//biomed/1472-684X-1-5.txt
technical//biomed/1476-4598-1-6.txt
technical//911report/chapter-13.4.txt
```

This searches the directory technical for all of type, f, which is all of the files. This gave us the output which showed us all of the files which is more then I showed but there was too many to put all of them.

I came across it while researching options for the find command in the [Linux manual page](https://man7.org/linux/man-pages/man1/find.1.html).

## -iname

```
slatermutunga@Slaters-MacBook-Pro docsearch % find technical/ -iname "chapter-8.txt"
technical//911report/chapter-8.txt
```

This searches the directory technical for a file named chapter-8.txt while ignoring case. This gave us the output which showed us how there is a file chapter-8.txt.

```
slatermutunga@Slaters-MacBook-Pro docsearch % find technical/ -iname "ChApTer-8.txt"
technical//911report/chapter-8.txt
```

This searches the directory technical for a file named ChApTer-8.txt while ignoring case. This gave us the output which showed us how there is a file chapter-8.txt, which shows how even though the case is different it still showed us the where the file is.

I came across it while researching options for the find command in the [Linux manual page](https://man7.org/linux/man-pages/man1/find.1.html).

## -not

```
slatermutunga@Slaters-MacBook-Pro docsearch % find technical/ -not -name "911report"
technical//biomed/1472-684X-1-5.txt
technical//biomed/1476-4598-1-6.txt
technical//911report/chapter-13.4.txt
technical//911report/chapter-13.5.txt
```

This searches the directory techincal for all files or directorys that aren't "911report". This gave us the output which shows how it skips over the 911report directory while printing out all of the other files and directorys.

```
slatermutunga@Slaters-MacBook-Pro docsearch % find technical/ -not -name "chapter-6.txt"
technical//911report/chapter-1.txt
technical//911report/chapter-5.txt
technical//911report/chapter-7.txt
```

This searches the directory techincal for all files or directorys that aren't "chapter-6.txt". This gave us the output which shows how it skips over the file chapter-6.txt while printing out all of the other files and directorys.

I came across it while researching options for the find command in the [Linux manual page](https://man7.org/linux/man-pages/man1/find.1.html).
