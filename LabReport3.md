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

