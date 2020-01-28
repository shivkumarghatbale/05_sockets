# sockets
Everything about the sockets, sockets at scale, blocking sockets vs non blocking sockets, synchronous vs asynchronous sockets

Topic 1) TCP sockets

e.g. Client is web browser & server is web server.

TCP sockets connection involves 3 phases
a) Connection Establishment
  Three way handshake to establish socket connection
  i) Client sends SYN message to server (asking server to open connection for client)
                  ->
           Seq#       SYN     ACK 
           9001        1       0
  ii) server acks it by sending ACK SYN message (asking client to open connection too)
                  <-
          seq#        SYN     ACK 
          5001         1      9002
  
  iii) client sends back ACK message to server acknowledging ACK SYNC message
                  ->
          seq#        SYN   ACK
          9002        0     5002
        
   Step 1,2 establish connection from client to server. Step 2,3 establish connection from server to client.
   
b) Data transfer
  Server sends the data to client. TCP guarantees data is successfully transferred & assembled back to recreate original message if data arrives out of order.
c) Connnection termination
   Four step process to terminate the connection
   i) Server send FIN ACK message to client stating server is done sending the data.
   ii) Client responds with ACK
   iii) When client completes the downloading the web page, it also sends FIN ACK to server.
   iv) Server responds back with ACK to terminate the connection.
   
   Hence TCP is connection oriented & reliable protocol.
