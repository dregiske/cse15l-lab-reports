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
