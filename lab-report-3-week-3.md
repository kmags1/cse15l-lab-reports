# Week 3 Lab Report 

## Part 1:

**Code for Search Engine:**
```
import java.io.IOException;
import java.net.URI;
import java.util.LinkedList;

class Handler implements URLHandler {

    LinkedList<String> items = new LinkedList<String>();
    
    public String handleRequest(URI url) {
        if (url.getPath().equals("/add")) {
            String[] parameters = url.getQuery().split("=");
            if(parameters[0].equals("s")){
                items.add(parameters[1]);
                return String.format("Added!");
            }
            return "Error!";
        } else if (url.getPath().equals("/search")) {
            String[] parameters = url.getQuery().split("=");
            if(parameters[0].equals("s")){
                String key = parameters[1];
                String ret = "";
                for (int i = 0; i < items.size(); i++) {
                    Boolean check = items.get(i).contains(key);
                    if(check == true){
                        ret += items.get(i) + " ";
                    }
                }
                return String.format(ret);
            }
            return "Error!";
        } else {
            return "404 Not Found!";
        }
    }
}


class SearchEngine {
    public static void main(String[] args) throws IOException {
        if(args.length == 0){
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new Handler());
    }
}
```

![Image](Lab2-part4a.png)

- handleRequest is the method being called iin SearchEngine
- The argument to the method is localhost:4000/add?s=anewstringtoadd. The values of the field (items) when this method is called is NULL.
- The values of the field (items) after this is anewstringtoadd, because this string is added to the field.

![Image](Lab2-part4b.png)

- handleRequest is the method being called iin SearchEngine
- The argument to the method is localhost:4000/. The values of the field (items) when this method is called is anewstring.
- The values of the field (items) after this is anewstring, so it hasn't changed.

![Image](Lab2-part4c.png)

- handleRequest is the method being called iin SearchEngine
- The argument to the method is localhost:4000/search?s=apple. The values of the field (items) when this mehtod is apple, pineapple and anewstringtoadd.
- The values of the field (items) after this is apple, pineapple and anewstring, so it hasn't changed.

## Part 2:

***Code of the test:***
![Image](Lab3-part1a.png)

***Failing output:***
![Image](Lab3-part1b.png)

***Code that needs fix:***
![Image](Lab3-part2bc.png)

***Fixed code:***
![Image](Lab3-part1c.png)

- The returned array needed to be reversed, basically swapped, but as it can be seen in the symptoms, it was not reversed. The bug was that the second half of the array was being copied to the first half in order, but when it was updated, the first half of the array was lost, so the new values that were copied into the first half are also copied into the second half, which basically means that the second half was never changed. I fixed that by swappinhg the values the values until the middle of the array was reached.


***Code of the test:***
![Image](Lab3-part3a.png)

***Failing output:***
![Image](Lab3-part3b.png)

***Code that needs fix:***
![Image](Lab3-part3bc.png)

***Fixed code:***
![Image](Lab3-part3c.png)

- The returned list needed to add the strings that had a length greater than 1 in the exact order. However, the bug is that the code was adding in reverse order. I fixed it by changing add(0, element) to add(element) which makes sure the string are added in order.