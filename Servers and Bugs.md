# Servers and Bugs

## Part 1 Implementation of String Server
The StringServer is implemented as below, and you can add strings via add-message command on the path
```
import java.io.IOException;
import java.net.URI;

class Handler implements URLHandler {
    StringBuilder result = new StringBuilder("");

    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            return "Out content is none";
        } else {
            System.out.println("Path: " + url.getPath());
            if (url.getPath().contains("/add-message")) {
                String[] parameters = url.getQuery().split("=");
                if (parameters[0].equals("s")) {
                    result.append(parameters[1]);
                    result.append("\n");
                }
                return result.toString();
            }
        }
        return "404 Not Found!";
    }
}

public class StringServer {
    public static void main(String[] args) throws IOException {
        if (args.length == 0) {
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }
        int port = Integer.parseInt(args[0]);
        Server.start(port, new Handler());
    }
}
```

Now we can use this server!
When I use javac and java commands like below, I add the first message.
```
% javac StringServer.java
% java StringServer 8293
```
<img width="488" alt="Screen Shot 2023-01-26 at 11 34 36 AM" src="https://user-images.githubusercontent.com/110661816/214932654-c150fb34-2bea-48c7-a5d3-47d6a03c25c9.png">

For this call, main method and handleRequest in the Handler class are called. Url input of handleRequest method is "http://localhost:8293/add-message?s=Oceanview", and the String array, parameters,
will be created when splitting with "=" as {s, Oceanview}. Therefore, parameter[0] is "s" and parameter[1] is "Oceanview". And the result StringBuilder was changed, in particular, appended a string, which becomes "Oceanview "

Then, I continue use add-message command, and below is the second adding operation.

<img width="496" alt="Screen Shot 2023-01-26 at 11 45 04 AM" src="https://user-images.githubusercontent.com/110661816/214934850-6a2e17dd-c5dd-40eb-82ef-b9954664f895.png">

In this operation, main method and handleRequest are still called. Url input of handleRequest method is "http://localhost:8293/add-message?s=Canyon Vista", and the String array, parameters,
will be created when splitting with "=" as {s, Canyon Vista}. Therefore, parameter[0] is "s" and parameter[1] is "Canyon Vista". And the result StringBuilder was changed, in particular, appended a string, which becomes

```
Oceanview (with a \n)
Canyon Vista (with a \n)

```

## Part 2 A Bug, Test and Debug
### I choose append method in LinkedListExample 
When we try to append the first node in the linkedList. It works well. And we can test this operation with the implementation of tester below.
```
@Test
    public void testLast(){
        LinkedList l1 = new LinkedList();
        l1.append(5);
        assertEquals(5, l1.first());
    }
```
And running this test, we can find that our append method passes this test.

<img width="461" alt="Screen Shot 2023-01-26 at 1 37 06 PM" src="https://user-images.githubusercontent.com/110661816/214956163-6f96792f-e56c-47ce-8613-c4e7fc13df83.png">

However, when we try to append multiple nodes, unexpected result will show up. I test multiple appending with this test method.
```
    @Test
    public void testMultipleAppend(){
        LinkedList l2 = new LinkedList();
        l2.append(5);
        l2.append(4);
        l2.append(3);
        l2.append(2);
        l2.append(1);
        assertEquals(5, l2.first());
        assertEquals(1, l2.last());
        assertEquals("5 4 3 2 1 ", l2.toString());
    }
```

After running the test, we found that there is OutOfMemory error, and the test failed. The test result is below.

<img width="674" alt="Screen Shot 2023-01-26 at 1 42 30 PM" src="https://user-images.githubusercontent.com/110661816/214957031-682a5049-4bcd-4abc-9d4c-9958ad8915b2.png">

OutOfMemory error usually caused by infinite loop. And our current append method is implemented as below:
```
public void append(int value) {
        if (this.root == null) {
            this.root = new Node(value, null);
            return;
        }
        // If it's just one element, add if after that one
        Node n = this.root;
        if (n.next == null) {
            n.next = new Node(value, null);
            return;
        }
        // Otherwise, loop until the end and add at the end with a null
        while (n.next != null) {
            n = n.next;
            n.next = new Node(value, null);
        }
    }
```

By looking the while loop, we found that we are creating a node after n constantly while we move one node forward in each iteration. As a result, the loop will never end. Also, the purpose of `n.next = new Node(value, null);` should be creating a new node with value we put at the end of the list. Thus, we need to execute this line at the end of our current list.

We can solve this bug by simply moving this line to the end of this method, where the while loop finishes execution, so this line will only run once at the time we expect. Below is the correct version of append method.
```
    public void append(int value) {
        if (this.root == null) {
            this.root = new Node(value, null);
            return;
        }
        // If it's just one element, add if after that one
        Node n = this.root;
        if (n.next == null) {
            n.next = new Node(value, null);
            return;
        }
        // Otherwise, loop until the end and add at the end with a null
        while (n.next != null) {
            n = n.next;
        }
        n.next = new Node(value, null);
    }
```
And we use testMultipleAppend above to test our new append method, and now we pass this test.

<img width="559" alt="Screen Shot 2023-01-26 at 2 09 26 PM" src="https://user-images.githubusercontent.com/110661816/214961804-d2371d6b-95a7-47a4-9901-1c9645f3a3ec.png">

So far, we have solved this bug.

## Part3 Reflection
In the lab of Week 2 and Week 3, I first learned the basic manipulation of url, and know clearly the composition of a url. Also, I've also learned to write a program that I didn't know how to write based on similar ones.
During this week, my ability to locate bug improves a lot. Besides, I become aware that I need to test my program systematically and in every possible legal aspects to ensure it is correct all the time. Before, I seldom consider many edge cases when testing my program, which is a significant flaw when coding.


