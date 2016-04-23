# jMessenger
JMessenger is conceptualized and is based on the Communication nature of Human Being and is an attempt to make the communication better.
jMessenger is mainly cotent of two parts 
1.Client module 
2.Server module

Features

    1.Handles multiple users at the same time
    2.Support for both public and private messages
    3.User signup and login available 
    4.Support for file transfer

Using the code

Run the jar files jMessenger.jar and jServer.jar and do the following:

    On jServer select "data.xml" as database file. This file contains usernames and passwords.
    On jMessenger select "History.xml" as history file. This file is used to save chat history.
    In many cases, if jMessenger cannot find the server then adjust firewall to give it network access.

Both applications are written in Netbeans and you can import source files in Netbeans to view and edit them.
Message structure

Each message in jMessenger has four fields:

    1.type: This can be set to message, login, newuser, etc.
    2.sender: The username of sender
    3.content: Actual content of the message
    4.Recipient: Username of recipient of the message
    
    
    
    
  ---> jServer

There are two main classes in jServer for handling connections and messages. On startup the SocketServer runs in a separate thread. The job of SocketServer is to wait for connections and for each connection start a new thread ServerThread. Once the connection is established, ServerThread will listen for any messages and hand it over to SocketServer to process. Also it will forward messages from other users to the connected user .

 ---> jMessenger

jMessenger first connects to the jServer, specified by its IP-address and port number. Arriving messages are then displayed on message board along with their senders.

When a user wants to send a file, first his request is sent via a message of type upload_req. The recipient then does the following:

    The recipient side sends its reply in a message of type upload_res
    If request is accepted then the recipient opens a new port
    For positive reply, recipient's IP address and port number is sent back
    The sender, on receiving positive reply connects to this socket and starts file upload

An advantage of this approach is that the clients can chat and transfer files at the same time. Unlike messages, files do not go through jServer.

  DRAWBACKS SUCKS 

Many people are confused why chat over different networks is not possible. To understand this, take the example of any web-server. For any browser to connect to a web-server, this server needs to have a global IP address so that it is visible on the Internet. Similarly jServer also is a application server and for chat over two different networks (say a campus LAN and DSL at your house), it also need to be run on a computer with a global IP address.

and ya that's it .
Cheers to JAVA :P



