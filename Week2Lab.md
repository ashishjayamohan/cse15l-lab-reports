# Week 2 & 3 - Testing

## 1. Simple Search Engine
In Week 2, we implemented an ultra-basic search engine to practice our use of `ssh` and `scp`. Using the structure of the given `Server.java` file, I was able to implement the search engine using the following code:

```
import java.io.IOException;
import java.net.URI;
import java.util.ArrayList;
import java.util.List;

class Handler implements URLHandler {
    List<String> list = new ArrayList<>();

    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            return String.format("Basic Search Engine");
        }
        else {
            System.out.println("Path: " + url.getPath());
            if (url.getPath().contains("/add")) {
                String[] parameters = url.getQuery().split("=");
                if (parameters[0].equals("s")) {
                    list.add(parameters[1]);
                    return String.format("%s added to the list", parameters[1]);
                }
            }
            if (url.getPath().contains("/search")) {
                String[] parameters = url.getQuery().split("=");
                List<String> ans = new ArrayList<>();
                if (parameters[0].equals("s")) {
                    for (String i: list) {
                        if (i.contains(parameters[1])) {
                            ans.add(i);
                        }
                    }
                }
                return String.join(" ", ans);
            }
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

You can run the above class using `javac SearchEngine.java` and `java SearchEngine <port-number>`. (*Note that you must pass in the desired port number as an argument into the command line - this value can be anything between 1024 and 49151*). Once you run the program, the `main` function is called - establishing the web server at the selected port and allowing you to view the live version of your project at `<host>:<port-number>`. Your screen should look somewhat like the one below:
![Image](./Images/basic-search-engine.png)

After getting the live version of the program running, you can append various paths to the end of the URL to achieve different results. There are 