Part 1:

Part 2:
The first bug I found was on the reversed function in ArrayExamples.java:

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
  
  The second bug I found was on the merge function in ListExamples.java:
   
  1. The failure-inducing input:
  @Test
       public void mergetest1()
       {
           List<String> listA =  List.of("a", "b", "g");
           List<String> listB =  List.of("c", "f", "w");
           List<String> listC =  List.of("a", "b", "c", "f", "g", "w");
           assertEquals (listC, ListExamples.merge(listA, listB));
       }
  
  2. The symptom:
  
  `initializationError(org.junit.runner.JUnitCommandLineParseResult)`
  `Caused by: java.lang.ClassNotFoundException: ListTest`
  
  3. The bug:
  ```
  while(index2 < list2.size()) {
      result.add(list2.get(index2));
      index1 += 1;
    }                            
  ```
  I replaced index1 with index2.
  
  4. Explain the connection between the symptom and the bug. Why does the bug cause that particular symptom for that particular input?
  
  The index that was being incremented was index 1 not index 2, which caused the error.
  

