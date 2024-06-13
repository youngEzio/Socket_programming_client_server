# Simple Socket Programming in Python
This repository contains two Python files, ```Client.py``` and ```Server.py```, that demonstrate basic client-server communication using sockets.

## Functionality
The Server.py script creates a server that listens for incoming connections on a specified port (default: 5000).
The Client.py script allows a user to connect to the server and send messages back and forth.
The server echoes back the received messages to the client.

## Running the Code

Clone this repository to your local machine.

Open two terminal windows.

In the first terminal, navigate to the project directory and run the server:
```python Server.py```

In the second terminal, navigate to the project directory and run the client:
```python Client.py```

## Interaction

In the client terminal, type a message and press Enter.
The message will be sent to the server and displayed in the server terminal.
The server will echo the message back to the client terminal.
You can continue sending messages back and forth until you type "bye" (case-insensitive) in the client terminal, which will terminate the connection.

## Code Breakdown:

### Client.py

Imports: Imports the socket module for network communication.

#### client_program function:
Establishes a socket connection with the server using socket.gethostname() (localhost) and port 5000.
Prompts the user for messages in a loop.
Sends the message to the server using client_socket.send().
Receives the server's response using client_socket.recv().
Prints the received data to the console.
Closes the socket connection when the user types "bye".

if __name__ == '__main__': block: Ensures the client_program function runs only when the script is executed directly (not imported as a module).

### Server.py

Imports: Imports the socket module for network communication.

#### server_program function:
Establishes a server socket using socket.socket().
Binds the socket to the hostname (localhost) and port 5000.
Listens for incoming connections with server_socket.listen(2) (maximum two connections).
Accepts a new connection using server_socket.accept().
Prints a message indicating the client's address.
Enters a loop to receive messages from the connected client.
Receives data from the client using conn.recv().
If no data is received, the loop breaks.
Prints the received message to the console.
Prompts the user for a response.
Sends the response to the client using conn.send().
Closes the connection with the client using conn.close().

if __name__ == '__main__': block: Ensures the server_program function runs only when the script is executed directly (not imported as a module).

## Customization

You can modify the port number in both files to use a different port for communication.
You can enhance the code to handle more complex message formats or error conditions.
Consider adding functionality like user authentication or message encryption for production use.

## Learning Objectives

This code provides a basic example of how to implement simple client-server communication using Python sockets. You can use this as a foundation to explore more advanced socket programming concepts and build more robust network applications.
