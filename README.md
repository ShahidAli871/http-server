# Http-server

I wanted to get into systems programming, so the first step was to understand C and learn everything there is to this language. So after referring to a few sources, the next step was to learn network programming. So I picked up beej's network programming guide to get things started.
This was a very useful way of getting to know the nature of C as a languauge and get used to it's environment.

I am just going to briefly list out all that I have learnt from the guide and from understanding how a simple HTTP server written in C.

- File Descriptors - What they are and they're singnifiance.
- Sockets - Stream sockets and Datagram sockets
- structs - the addresses and information about the address are stored in these structs.
- fucntions - htons(),htonl(),ntohs(),ntohl()
## System Calls
1. getaddrinfo() - this fills out the structs that will be used in subsequent sys calls for establishing a connection.
2. socket() - this gets the socket file descriptor for us.
3. bind() - associating the file descriptor with a port.
4. connect() - connect to a remote host.
5. listen() - we run this on the server, in order to listen to incoming connection requests.
6. accept() - this accepts the incoming request and returns a new socketfd, which will be used for communication.
7. send() & recv() - These facilitate communication over stream and conencted datagram sockets. The new socketfd returned by the accept () call is used in these functions.
8. close() is used to close a socket i.e. free the socket descriptor.
9. shutdown() is to makes the socketfd unavailable for communication.

Once we have got all this covered is we can understand how a simple server code can be written in C.
