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
I choose append method in LinkedListExample 


