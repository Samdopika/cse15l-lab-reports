**Part 1:**
---
My web server can add the input strings to a list and in the function it returns the strings that have the searched substring. 
* **add function:** In order to add a string the user must run the following URL and query: `http://localhost:4000/add?input=anewstringtoadd` 
* **search function:** In order to add a string the user must run the following URL and query: `http://localhost:4000/search?input=app` 

The code below is my `SearchEngine.java`:
```
import java.io.IOException; 
import java.net.URI; 
import java.util.ArrayList;

class Handler implements URLHandler { 
    ArrayList<String> words = new ArrayList<String>();
    public String handleRequest(URI url) {
        System.out.println("Path: " + url.getPath());
        if (url.getPath().contains("/add")) {
            String[] parameters = url.getQuery().split("=");
            if (parameters[0].equals("input")) {
                words.add(0, parameters[1]);
                return parameters[1] + " is added";
            }
        }
        else if(url.getPath().contains("/search")){
            String[] parameters = url.getQuery().split("=");
            ArrayList<String> searchedWords = new ArrayList<String>();
            if (parameters[0].equals("input")){
                for(int i = 0; i < words.size(); i++){
                    if(words.get(i).contains(parameters[1])){
                        searchedWords.add(0, words.get(i));
                    }
                }
            }
            return searchedWords.toString();
        }
         else if (url.getPath().equals("/")) {
            return "Search or add a word";
         }
        else
        {
            return "404 Not Found!";
        }
        return "";
    }
}
class SearchEngine{
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
* **In following there are screenshots are the server running and using the `add` and `search` function:**
*    * In this screenshot I've used the `add` command. By doing that i am adding the string "anewstringtoadd"(argument) to the arraylist. 
![image](Lab3-images\anewstringtoadd.jpg)

*   * In this screenshot I've used the `add` command. By doing that i am adding the string "apple"(argument) to the arraylist.
![image](Lab3-images\apple.jpg)

*   * In this screenshot I've used the `add` command. By doing that i am adding the string "pineapple"(argument) to the arraylist.
![image](Lab3-images\pineapple.jpg)

*  **In this screenshot I've used the `search` command. By doing that i am searching a string as a substring in the arraylist which contains my added inputs. The result will be any string in the arraylist that contains the input i searched.**
*   * In this example i searched the string `app` which since is a substring for both `pinapple and apple` the result would be expected to be `[pineapple,apple]`. 
![image](Lab3-images\Search(app).jpg)


**Part 2:**
---