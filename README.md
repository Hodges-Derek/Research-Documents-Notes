# Research-Documents-Notes

May 9, 2015
Client/Server Socket IO
This is the topic that I have been trying to get a basic understanding of for now so that I would be able to explain it to my group so they could understand as well. I feel as though I have a lot left to learn about this topic and so I have no code as of yet that I am able to show because I am still trying to understand it for myself. What I have learned about it so far is that Socket IO is essential when you have an app that uses real time. For example if you have multiplayer game where you have two players that need to interact in real time. Another example of when socket IO should be used in in a chat application when it is key for people to be able to communicate in real time. I have chosen the same topic for next as well because I want to be able to really understand socket IO and be able to create some code for it and better understand it. Maybe next time I will choose a topic that I kind of have an idea about so it won’t be so difficult.
-----------------------------------------------------------------------------------------------------------------------------

May 16, 2015
<h1>SOCKET.IO</h1>
<p>Writing a chat application with popular web applications stacks like LAMP (PHP) has traditionally been very hard. It involves polling the server for changes, keeping track of timestamps, and it’s a lot slower than it should be.</p>

<p>Sockets have traditionally been the solution around which most real time chat systems are architected, providing a bi-directional (two way) communication channel between a client and a server.</p>

<p>This means that the server can push messages to clients. Whenever you write a chat message, the idea is that the server will get it and push it to all other connected clients. So in other wards the server can recieve the message being sent and then relay that message to all of the clients that are connected to the chat session.</p>

<h3>Socket.IO is composed of two parts:</h3>
<p>•	A server that integrates with the Node.JS HTTP Server: socket.io</p>
<p>•	A client library that loads on the browser side: Socket.io-client</p>

<p>The main idea behind Socket.IO is that you can send and receive any events you want, with any data you want. Any objects that can be encoded as JSON will do, and binary data is supported too.</p>

<h3>Excluding people in the chat:</h3>
  <p>io.on('connection', function(socket){<br>
  socket.broadcast.emit('hi');<br>
});</p>
------------------------------------------------
<h3>To send to everyone:</h3>
  <p>io.on('connection', function(socket){<br>
  socket.on('chat message', function(msg){<br>
    io.emit('chat message', msg);<br>
  });<br>
});</p>
