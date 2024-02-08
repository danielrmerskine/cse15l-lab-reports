## CSE 15L Lab Report 3
### Part 1 - Bugs:
#### Failure-Inducing Input Example:
```
@Test
public void testReversed2() {
  int[] input1 = { 1, 2, 3 };
  assertArrayEquals(new int[]{ 3, 2, 1 }, ArrayExamples.reversed(input1));
}
```

#### Input that doesn't Induce a Failure:
```
@Test
public void testReversed3() {
  int[] input1 = { 0 };
  assertArrayEquals(new int[]{ 0 }, ArrayExamples.reversed(input1));
}
```

#### The Symptom:
![screenshot of sympton](week5image1.png)

#### The Bug: 
```
static int[] reversed(int[] arr) {
  int[] newArray = new int[arr.length];
  for(int i = 0; i < arr.length; i += 1) {
    arr[i] = newArray[arr.length - i - 1];
  }
  return arr;
}
```
```
static int[] reversed(int[] arr) {
  int[] newArray = new int[arr.length];
  for(int i = 0; i < arr.length; i += 1) {
    newArray[i] = arr[arr.length - i - 1];
  }
  return newArray;
}
```
##### Brief Description:
This change fixes the method `reversed()` because the original method sets `arr[i]` equal to newArray[arr.length - i - 1] but `newArray` 
is an empty array that is the same length as `arr`. The new method instead sets `newArray[i]` equal to `arr[arr.length - i - 1]`. Then,
I returned `newArray` instead of `arr` since that is the correct reversed array.

### Part 2 - Researching Commands:
