# SocketProgramming
A client-Server socket program in C

1. Server sets up a TCP socket and listens for client connections.
2. The client creates a socket and initiates the TCP connection. Server have the capability to handle multiple concurrent clients (multithreaded, concurrent server). The server accepts the client connection, hence, a new socket is created with 4 tuples (serverip, server listening port, client ip, client port). Server creates a new thread that continues to process the client connection.The original server socket continues to listen on the same listening port for newer
incoming client connections.
3. After the client connection is established, the client sends a request to the server to get the information about server’s top “N” CPU consuming processes.
4. Server finds out the top “N” CPU consuming processes (user+kernel CPU time), gathers information such as process name, pid (process id), and CPU usage of the process in user & kernel mode. Server writes this information to a local file.
5. Server sends the file created in step 4 to the client. Client stores it in its local drive.
6. Client identifies the process that consumes the highest amount of CPU (similar to step 4, but reports only the top CPU consuming process) and sends the process information(process name, pid and CPU usage) to the server.
7. The client closes the connection.
