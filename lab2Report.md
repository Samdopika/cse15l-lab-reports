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

> In this screenshot I've used the `add` command. By doing that i am adding the string "anewstringtoadd"(argument) to the arraylist.(URL:` localhost:4000/add?input=anewstringtoadd`) 
![image](Lab3-images\anewstringtoadd.jpg)(parameters:`[anewstringtoadd]` )
We are calling handleRequest for all of them. 


> In this screenshot I've used the `add` command. By doing that i am adding the string "pineapple"(argument) to the arraylist.(URL:` localhost:4000/add?input=pineapple`)(parameters:`[anewstringtoadd, pineapple]` )
![image](Lab3-images\pineapple.jpg)

> In this screenshot I've used the `add` command. By doing that i am adding the string "apple"(argument) to the arraylist.(URL:` localhost:4000/add?input=apple`)(parameters:`[anewstringtoadd, pineapple, apple]` )
![image](Lab3-images\apple.jpg)


*  **In this screenshot I've used the `search` command. By doing that i am searching a string as a substring in the arraylist which contains my added inputs. The result will be any string in the arraylist that contains the input i searched.**
>  In this example i searched the string `app` which since is a substring for both `pinapple and apple` the result would be expected to be `[pineapple,apple]`. (URL:` localhost:4000/search?input=app`)(searchedWords:`[pinapple, apple]` )
![image](Lab3-images\Search(app).jpg)


**Part 2:**
---
**`reversedInPlace` Method**
* **Failure-inducing Input:**
>  This screenshot is of a test. The array i am testing is [1,2,3,4,5] <mark>(basically any array that has distinct elements and has length greater than 2)</mark>. The expected output is [5,4,3,2,1]:
![image](Lab3-images\Failure-inducingInput.jpg)

* **Symptom:**
>  After running the test the error indicated that instead of [2], [4] was printed which COULD mean the current output is [1,2,3,2,1]:
![image](Lab3-images\Symptom.jpg)

* **This is how i tried to fix the bug:**
>  In this screenshot i proceeded multiple modifications to fix the bug. but in short, the issue was that it stops swapping once it crosses middle element because the for loop swaps
it back thus the original method would give us a wrong output:
![image](Lab3-images\FixedBug.jpg)

* **Explanation:**

The symptom was that instead of [4] we were getting [2] which means the method doesn’t keep the value of the swapped portion, so the other half of the array would be overridden. (**note**: by front and end i mean the front portion and end portion) So i created a letterCount integer to store the value of the end. then put the value from the front to the end and put the letterCount in the front. I also devided the arr.length in the for loop by 2 so i will not past after going through half of the array.  


**`reversed` Method**
* **Failure-inducing Input:**
>  This screenshot is of a test. The array i am testing is [1,2,3,4,5]. The expected output is [5,4,3,2,1]:
![image](Lab3-images\reversedtest.jpg)

* **Symptom:**
>  After running the test the error indicated that instead of [5], [0] was printed which COULD mean the current output is [0,0,0,0,0]:
![image](Lab3-images\reversedSymptom.jpg)

* **This is how i tried to fix the bug:**
>  In this screenshot i proceeded to fix the bug, before, the values of each index of `arr` were updated at eachother. But after switching assignment of the array values:
![image](Lab3-images\fixedreverse.jpg)

* **Explanation:**

The symptom was that instead of [5] we were getting [0] which means the method is intended to create a new array called `newArray` and copy the elements of `arr` into `newArray`. Although it is copying emplty elements from `newArray` into `arr`. The reason why we see 0 instead of the numbers in the `arr` is because of the empty elements in `newArray`. 



<mark>**filter is EXTRA**</mark>

**`filter` Method**
* **Failure-inducing Input:**
>  This screenshot is of a test i have built using `wordFunction` to check if the words in the array contain `sh` :
![image](Lab3-images\filtertest.jpg)

* **Symptom:**
>  After running the test, the value at result.get(0) turned out to be "Brian", instead of "Saman".:
![image](Lab3-images\filtersymptom.jpg)

* **This is how i tried to fix the bug:**
>  In this screenshot i proceeded to fix the bug:(.add is changed)
![image](Lab3-images\fixedfilter.jpg)

* **Explanation:**

In `wordFunction` i basically am filtering the strings in the array that has `sh` in it. the firts thing i noticed was that the .add function contains an index when called in the method, which causes that everytime a new value is passed through the filter, the new value is added at the index. which was an issue. The other problem is `0` in the `result.add` that is called. this causes every valid string to be added to the front, which makes the new list reversed.