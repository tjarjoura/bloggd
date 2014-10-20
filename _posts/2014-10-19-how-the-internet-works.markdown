---
layout: post
title:  "How the Internet Happens"
date:   2014-10-17 20:00:33
categories: internet tcp ip data bits 
---
The internet is one the most prevalent phenomena of modern day society. Before I really understood what was going on with it, I always assumed that it was a very complex system. But really it's very simple. In this post I'm going to attempt to explain it from the bottom up. By the end you'll hopefully be able to visualize what's going on under the hood when you perform common internet tasks. These could be anything like sending a search request to google, navigating to a website in your browser, or downloading a file. No programming or technical experience necessary.

I'm going to start our story with the notion of a bit. Computers represent data using bits, which are implemented in modern day computers using electricity. Theoretically, a bit can represent one of two values(typically 1 or 0), and physically this is implemented by the presence or abensce of electricity. Think of a tiny lightbulb that you turn on or off.

If we put two bits next to each other, the two of them combined can now represent 4 different values! How? Well we can have: (1 and 0, 1 and 1, 0 and 0, or 0 and 1). Following this same logic, everytime we add a bit we can represent 2 times as many values. Note that these values can be anything. They can be letters of the alphabet, integers, color codes, instruction codes, etc. Using different forms of logic and technoology, we can interpret and utilize these values in a variety of cool an awesome ways. Your monitor displays pixels by accepting a series of numbers representing the color as input. These "numbers" are merely bits implemented as electrical signals! So if you save the bits, you can make your monitor display the same stuff again and again.

So we have these bits, which from now on I'm going to refer to as data. We can represent so many different things with them, but we need a way to save them and access them later. Modern computers have operating systems like Linux, OS X, or Windows. These are basically programs that run on your computer and make using its set of powerful hardware easy and user-friendly. Computer typically come with a hard drive, which you can think of as a big set of "slots" that can be set to 0 or 1 and they'll stay that way until you set them to something else. The operating system will provide you with a way to access these slots in a way that makes sense. This is called a "file-system". You can create files that represent a bunch of these slots, give the file a name, and you can 'read' or 'write' to these files, which will change the value of the slots. Then whenever you want to remember what you wrote you can just access the file by its name.

Now we can save our data, maybe we want to share it with someone thousands of miles away. This is where the concept of the internet comes along. As it turns out, some really cool technology for sending signals between computers was developed in the second half of the 20th century. The basic hardware implementing this is known as the "Link Layer" of the internet! We generally think of the internet as containing 4 layers -- the Link Layer, the Internet Layer, the Transport Layer, and the Application Layer.

The Link Layer is pretty intense in terms of the technology involved, and it is implemeneted in several different ways. I admittedly don't know much about how it actually works, but really all you need to know is that it is the actual transmission of data(ie. signals representing bits, representing in turn whatever you need them to!)

The Internet Layer is there so that the data knows where to be sent. There is something known as the "ip protocol" which describes the structure of bits that different programs should be sending through their hardware. You may have heard of an "ip" address, but if not you should know that every computer connected to the internet has one. They are used to discriminate where to send your data to.

The Transport Layer is the next level up. Sending data from one computer to another is fine, but we also want the other computer and programs on it to recognize that they received the data. The Transport Layer consists of a bunch of different protocols that programs can use to connect with one another. It might be hard to understand why this is necessary from that description alone, so I'm going to present an example. Think of the computer which holds a website. The computer itself needs a way to do all the processing relating to generating the website and sending it back to various internet browsers, which are located on other computers. So a program called a "web server" is run on the first computer.

Now imagine that there is another web server running on this computer for another website. When the computer receives data from the internet, it could be intended for either web server. THAT'S where the Transport Layer comes into play. This layer is typically managed by the operating system of the computer. Like how the operating system has files to deal with the hard drive, it will also implement "files" that represent a line of communication between two programs. Based on the protocol used(the most common one is called TCP), the bits sent between each computer will be structured so that the operating system on each end will know which "file" a certain chunk of data is supposed to go to. Then programs will only read the data intended for them.

Finally we have the Application Layer. This one is pretty diverse. Basically there are many different "services" provided by the internet. Some examples include the world wide web, downloading files, using a computer remotely, or chatting with people. Each of these services are only made possible by the presence of two different kinds of programs on different machines. We call these "clients" and "servers". They need a way to communicate with each other given their specific task, and so different protocols were developed for that. Again a protocl basically defines how programs should structure their data to signal what they want to do.

Some examples:

* IRC, short for Internet Relay Chat, is a protocol that defines how programs can access a server, send messages to it, see the messages other people have sent to it, and many other things.
* HTTP, short for Hypertext Transfer Protocol, defines how web browers and web servers should communicate.
* FTP, short for File Transfer Protocol, defines how ftp clients should request to "download"(which is basically just copying bits) a file(a set of bits) from a server.

That wraps this up. Here's some further reading for those who are interested. I don't know your skill level, so some of it is relatively advanced:

[Wikipedia - Internet Protocols](http://en.wikipedia.org/wiki/Internet_protocol_suite#Abstraction_layers)
[TCP/IP Illustrated](https://leaksource.files.wordpress.com/2014/08/tcp_ip-illustrated-vol-3.pdf) (For those who know how to program)
[Internet History](http://www.livinginternet.com/i/ii.htm)
[Unix Network Programming](http://scoecomp.files.wordpress.com/2014/02/2003-unix-network-programming-vol-1-3rd-ed.pdf) (For those who know how to program)

