
Part 2:
The first bug I found was on the reversed function:

1. The failure-inducing input: 
@Test
  public void testReversed() {
    int[] input1 = {1,2,3,4};
    assertArrayEquals(new int[]{4,3,2,1}, ArrayExamples.reversed(input1));
  }
  
 2. The symptom: 
 `arrays first differed at element [0]; expected:<4> but was:<0>`
 `Caused by: java.lang.AssertionError: expected:<4> but was:<0>`
 
 3. The bug:
  ```
  for(int i = 0; i < arr.length; i += 1) {
      newArray[arr.length - i - 1] = arr[i];
    }
    return newArray;
  ```
  I interchanged newArray and the index for arr and replaced the return statement from arr to newArray.
  
  4. Explain the connection between the symptom and the bug. Why does the bug cause that particular symptom for that particular input?
     
     It was not creating a new array or returning a new array it just returned the original array arr.
  The second bug I found was on the 

