Part 1:
Code:

import java.io.IOException;
import java.net.URI;
import java.util.ArrayList;
```
class Handler implements URLHandler 
{
    int num = 0;
    ArrayList<String> list = new ArrayList<String>();
    ArrayList<String> elements = new ArrayList<String>();

    public String handleRequest(URI url) 
    {
        if (url.getPath().equals("/")) 
        {
            return String.format("Search or Add something to the list");
        } 
        else if (url.getPath().contains("/search")) 
        {
            String[] trySearch = url.getQuery().split("=");
            elements.clear();
            if (trySearch[0].equals("s")) 
            {
                if (list.contains(trySearch[1])) 
                {
                    for (String element : list)
                    {
                        if(element.contains(trySearch[1])) 
                        {
                            elements.add(element);
                        }
                    }
                    return String.format("Found!: '%s'", elements);
                }
                return String.format("searching: '%s'. No results.", trySearch[1]);
            }
            else 
            {
                return String.format("Unable to search.");
            }

        } 
        else 
        {
            System.out.println("Path: " + url.getPath());
            if (url.getPath().contains("/add")) {
                String[] parameters = url.getQuery().split("=");
                if (parameters[0].equals("s")) {
                    list.add(parameters[1]);
                    return String.format("Added '%s'. Here is the list: %s", parameters[1], list);
                }
            }
            return "404 Not Found!";
        }
    }
}

class SearchEngine {
    public static void main(String[] arg) throws IOException 
    {
        if(arg.length == 0){
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(arg[0]);

        Server.start(port, new Handler());
    }
}
```
![image12](https://user-images.githubusercontent.com/114322700/195967760-371840aa-00de-416d-94d9-7b921909e262.png)
![image11](https://user-images.githubusercontent.com/114322700/195967937-1b077cce-3cb8-41ec-b74d-89ce08b2d45f.png)

For the /add and /search I used the handleRequest function and the argument of the method I am using my page URL. The URL changes only if I edit it, it does not change when the function is called. If the values in the array change, by the time the request is done processing it changed by adding another value in the array if I used /add or displaying the required element when I used /search.

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
  

