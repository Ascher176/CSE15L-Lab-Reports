## Part 1
![Image](codeStringServer.jpg)  

* Integer.parseInt(args[0]) is called to get a port number as an integer from the passed arguments. For both screenshots it gets "2012" (a String type) and converts it to integer. The value is stored in port variable.
* Server.start(port, new Handler()) starts a server for both screenshots. The parameters are port and a new Handler() object.
* handleRequest(URI url) is a method within the Handler class. It takes URL as a parameter (url) and performs these operations:
  1. url.getPath() returns pathname as a String
  2. url.getPath().equals("/") compares the pathname with "/". For both methods it returns false since we use the "/add-message" command.
  3. System.out.println("Path: " + url.getPath()) prints out the path name
  4. url.getPath().contains("/add-message") checks if the pathname contains the "/add-message" command. For both screenshots the method will return true.
  5. url.getGuery() returns query as a String. For screenshot 1 it is s=Hi!, for 2 - s=My name is Anya Chernova.
  6. url.getQuery().split("=") splits query around "=". For screenshot 1 we get ["s", "Hi!"], for 2 - ["s", "My name is Anya Chernova"].
  7. parameters[0].equals("s") checks if the first parameter is "s". The method returns true for both screenshots.
  8. The String variable str which is initially empty becomes str + parameter[1]. For screenshot 1 str is updated from "" to "Hi!". For 2 - from "Hi!" to "Hi!\nMy name is Anya Chernova".
  9. String.format(str) returns formatted string. It is what the handleRequest(URI url) returns for both cases and is what we see on the screenshots. 
![Image](StringServer1.jpg)
![Image](StringServer2.jpg)  

## Part 2
Code before:
```
public class ArrayExamples {
    static void reverseInPlace(int[] arr) {
        for(int i = 0; i < arr.length; i += 1) {
            arr[i] = arr[arr.length - i - 1];
        }
    }
}  
```  

JUnit test with input that induces an error:
```
import static org.junit.Assert.*;
import org.junit.*;

public class ArrayTests {
    @Test 
    public void testReverseInPlace1() {
        int[] input1 = {5, 16, 29, 11, 24};
        ArrayExamples.reverseInPlace(input1);
        assertArrayEquals(new int[]{24, 11, 29, 16, 5}, input1);
    }
}
```   
JUnit test with input that does not induce an error:
```
import static org.junit.Assert.*;
import org.junit.*; 

public class ArrayTests {
    @Test 
    public void testReverseInPlace2() {
        int[] input2 = {3};
	ArrayExamples.reverseInPlace(input2);
	assertArrayEquals(new int[]{3}, input2);
    }
}
```  
Tests output:
![Image](tests.jpg)  

Code after:  
```
public class ArrayExamples {
    static void reverseInPlace(int[] arr) {
        for(int i = 0; i < arr.length/2; i += 1) {
            int temp = arr[i];
            arr[i] = arr[arr.length - i - 1];
            arr[arr.length - i - 1] = temp;
        }
    }
}
```  
The code before was just assigning the value of the element at index i to the value of the element at index arr.length - i - 1 instead of swapping them. To actually swap them we need to create an extra variable which will store the initial value of the element at index i, so after we assign the value of the arr.length - i - 1 element to i element, we can change the value of the arr.length - i - 1 element to the initial velue of the i element. In addition, in the loop the condition arr.length < 0 is incorrect since when we reach the middle of the array the values are gonna be swapped back to the original, so the condition is supposed to be arr.length/2 < 0.
