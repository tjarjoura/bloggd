---
layout: post
title: "All About IRC"
date: 2014-11-09 16:51:08
categories: internet irc chat protocol server
---

These past few days, I've been working on an implementation of the [IRC protocol](https://tools.ietf.org/html/rfc1459). IRC is one of many application-layer protocols that exist(other examples include Telnet, FTP, and the world wide web's HTTP). All of these specify, in a very detailed manner, how a server and a client should communicate with each other in order to provide some sort of service to the user. The server and client are merely two user processes that share a line of communication, a "connection" if you will.

IRC stands for Internet Relay Chat. It is one of the older internet applications, dating back to the late 80s when most people did not have internet access and the web was non existant. It provides a way for several users to communicate with each other by sending messages to a central IRC network. IRC networks consist of one or more IRC server processes which are connected to one another and pass messages back in forth. Then a user with an IRC cliet program on their computer could use it to connect to this network via one of the servers.

The users(client programs) can then all join channels, or create their own. Then, by sending messages to these channels, the server will relay the message to all of the other users joined to these channels. This has the effect of providing "chat rooms" for people. 

The way this is implemented is very specific. The server basically acts as a shell for the client, which can send it commands until it decides to disconnect. The server has a basic state that it keeps track of. Basically, this consists of a list of clients which are currently connected to it, a nickname for each of the clients, a list of channels which exist on the server, a name for each of the channels, and for each channel a list of clients that are joined to it.

Each message that the client sends it will either send back some sort of response(could be an error response or some sort of information about the server), change the state of the server, prompt the server to send a message to other clients, or some combination of these. The basic commands are:

* NICK - changes/sets the nickname associated with the client
* JOIN - adds the client to the channel specified
* PART - removes a client from the channel specified
* PRIVMSG - sends a message to the specified recipient(typically a channel or nickname)

The actually protocol provides for a lot more than I've described here, but this is the basic model. If you're interested, I encourage you to read the RFC I linked above. For those who are users of IRC but maybe didn't understand how it was implemented, I hope I have demystified it a bit.

Further reading:

[History of IRC](http://daniel.haxx.se/irchistory.html)
[RFC 2810 - IRC Architecture](https://tools.ietf.org/html/rfc2810)
[RFC 2811 - IRC Channel Management](https://tools.ietf.org/html/rfc2811)
[RFC 2812 - IRC Client Protocol](https://tools.ietf.org/html/rfc2812)
[RFC 2813 - IRC Server Protocol](https://tools.ietf.org/html/rfc2813)
