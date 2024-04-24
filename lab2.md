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
Screenshot 1:
-We call the class ```ChatServer``` with the ```main``` method which starts a new server with the given port number and then uses the class ```Handler``` which contains the method ```handleRequest``` which is the second method being called.
-For the ```main``` method it takes the ```args[0]``` which should be a number between 1024 and 49151 to create the new remote server, in this case 4000. And the method ```handleRequest``` uses the URL as ```args```, more specifically the query of the URL to execute the method. In this case, ```/add-message?s=Hello&user=Dre```. ```handleRequest``` uses ```messages``` class field as well.
-The revelant field ```messages``` gets changed from the method ```handleRequest``` by spilting the argument into parts and strategically adding these parts into the field ```messages```. Initially, ```messages``` was an empty string, which is then filled with ```Dre: Hello```.
