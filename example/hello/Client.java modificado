package example.hello;

import java.rmi.registry.LocateRegistry;
import java.rmi.registry.Registry;

public class Client {

    private Client() {}

    public static void main(String[] args) {

        System.out.println("Initiating client");
        
        String host = (args.length < 1) ? null : args[0];
        try {
            Registry registry = LocateRegistry.getRegistry(host);
            System.out.println("Registry has been located");
            Hello stub = (Hello) registry.lookup("Hello");
            System.out.println("Found server");
            String response = stub.sayHello();
            System.out.println("response: " + response);

            int resp = stub.soma(100,1000);
            System.out.println("Response from soma: " + resp);

          //mudança no código 
          boolean resultadoPar = stub.isPar(42);
          System.out.println("O número 42 é par? " + resultadoPar);

            
        } catch (Exception e) {
            System.err.println("Client exception: " + e.toString());
            e.printStackTrace();
        }
    }
}
