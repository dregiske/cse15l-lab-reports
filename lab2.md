Lab Report 2

Part 1:
```
import java.io.IOException;
import java.net.URI;

class Handler implements URLHandler {
    String messages = "";

    public String handleRequest(URI url){
        if (url.getPath().equals("/")){
            return String.format("ChatServer online");
        }
        else if (url.getPath().equals("/add-message")){ //  /add-message?s=Hello&user=Dre
            String[] parameters = url.getQuery().split("&");
            if(parameters[1].contains("user")){
                String[] param = parameters[1].split("=");
                messages += String.format(param[1] + ": ");
            }
            if (parameters[0].contains("s")){
                String[]param = parameters[0].split("=");
                messages += String.format(param[1] + ".\n");
            }
            return messages;
        }
        else{
            return "404 not found";   
        }
    }
}

class ChatServer{
    public static void main(String[] args) throws IOException{
        if(args.length == 0){
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }
        int port = Integer.parseInt(args[0]);

        Server.start(port, new Handler());
    }
}
```

Screenshot 1: https://dregiske.github.io/cse15l-lab-reports/lab2-screenshot-pt1.png (repository png)
![lab2-screenshot-pt1](https://github.com/dregiske/cse15l-lab-reports/assets/146780188/990540bd-8f94-4a5e-a505-81da510cb002)

We call the class ```ChatServer``` with the ```main``` method which starts a new server with the given port number and then uses the class ```Handler``` which contains the method ```handleRequest``` which is the second method being called.

For the ```main``` method it takes the ```args[0]``` which should be a number between 1024 and 49151 to create the new remote server, in this case 4000. And the method ```handleRequest``` uses the URL as ```args```, more specifically the query of the URL to execute the method. In this case, ```/add-message?s=Hello&user=Dre```. ```handleRequest``` uses ```messages``` class field as well.

The relevant field ```messages``` gets changed from the method ```handleRequest``` by splitting the argument into parts and adding these parts into the field ```messages```. In my code, it splits the query by the "&" which gives creates a ```String``` array called ```parameters```, ```parameters = ["s=Hello", "user=Dre"]```. The method then takes ```parameters[1]``` and splits it further by the "=" into a new ```String``` array called ```param```, ```param["user", "Dre"]```. Then it takes ```param[1]``` and adds it to ```messages``` with a ```:``` to acompany it. It then takes ```parameters[0]``` and splits that by the "=" to create a new ```String``` array also called ```param```, ```param = ["s", "Hello"]```. It adds ```param[1]``` to ```messages``` and creates a new line with ```\n```. Initially, ```messages``` was an empty string, which is then filled with ```Dre: Hello```. In the end it returns ```messages``` which is displayed on the remote server.

Screenshot 2: https://dregiske.github.io/cse15l-lab-reports/lab2-screenshot-pt2.png (repository png)
![lab2-screenshot-pt2](https://github.com/dregiske/cse15l-lab-reports/assets/146780188/7752a438-b63c-461b-8bd9-a450e32b6fc3)

We call the class ```ChatServer``` with the ```main``` method which starts a new server with the given port number and then uses the class ```Handler``` which contains the method ```handleRequest``` which is the second method being called.

For the ```main``` method it takes the ```args[0]``` which should be a number between 1024 and 49151 to create the new remote server, in this case 4000. And the method ```handleRequest``` uses the URL as ```args```, more specifically the query of the URL to execute the method. In this case, ```/add-message?s=Hey!%20Did%20you%20finish%20lab%20report%202?&user=John```. ```handleRequest``` uses ```messages``` class field as well.

The relevant field ```messages``` gets changed from the method ```handleRequest``` by splitting the argument into parts and adding these parts into the field ```messages```. In my code, it splits the query by the "&" which gives creates a ```String``` array called ```parameters```, ```parameters = ["s=Hey!%20Did%20you%20finish%20lab%20report%202?", "user=John"]```. The method then takes ```parameters[1]``` and splits it further by the "=" into a new ```String``` array called ```param```, ```param["user", "John"]```. Then it takes ```param[1]``` and adds it to ```messages``` with a ```:``` to acompany it. It then takes ```parameters[0]``` and splits that by the "=" to create a new ```String``` array also called ```param```, ```param = ["s", "Hey!%20Did%20you%20finish%20lab%20report%202?"]```. It adds ```param[1]``` to ```messages``` and creates a new line with ```\n```. Initially, ```messages``` contained ```Dre: Hello```, which is then filled with ```Dre: Hello\n John: Hey! Did you finish lab report 2?```. In the end it returns ```messages``` which is displayed on the remote server.

Part 2:

```ls``` absolute path with private keys:
![lab2-screenshot-pt3](https://github.com/dregiske/cse15l-lab-reports/assets/146780188/bdb7df07-e26f-45e4-b04a-d0b63202382d)
https://dregiske.github.io/cse15l-lab-reports/lab2-screenshot-pt3.png (repository png)

```ls``` absolute path with public keys:
![lab2-screenshot-pt4](https://github.com/dregiske/cse15l-lab-reports/assets/146780188/f96d5142-4efc-49d9-9f63-e553889c8617)
https://dregiske.github.io/cse15l-lab-reports/lab2-screenshot-pt4.png (repository png)

Login to ``ieng6``` without password:
![lab2-screenshot-pt5](https://github.com/dregiske/cse15l-lab-reports/assets/146780188/c4ef045a-9d4c-4b6f-a297-41c3ff6344cf)
https://dregiske.github.io/cse15l-lab-reports/lab2-screenshot-pt5.png (repository png)

Part 3:

In lab 2 I learned how to log into my own ieng6 account. In lab 3 I learned how to set my own key to avoid password logins. 
