# Introduction to Node.js

What is Node.js? # Node.js is a JavaScript runtime built on Chrome's V8 JavaScript engine. This of-course does not make sense to you, but I am sure you will understand it.

In Stack Overflow, Node.js is an event-based, non-blocking, asychronous I/O runtime that uses Google's V8 JavaScript engine and libuv library.

## The V8 Engine

The V8 Engine is the open source JavaScript engine that runs in Google Chrome and other Chromium-based web browsers, including Brave, Opera, and Vivaldi. It was designed with performance in mind and is responsible for compliling JavaScript directly to native machine code that your computer can execute.

When we say that Node is built on the V8 engine, we don't mean that Node programs are executed in a browser. They aren't. Rather, the creator (Rayn Dahl) took the v8 engine and enhanced it with various fratures, such as a [file system API](https://www.sitepoint.com/useful-built-in-node-js-apis/), an HTTP library and a number of operating system-related utility methods.

This means that Node.js is a program we can use to execute JavaScript on our computers. In other words, it's a JavaScript runtime.

## Node.js Let's Us Run JavaScript on the Server

Next we come to one of the biggest use cases for Node.js - running JavaScript on the server. This iisn't a new concept n and was irst attempted by nNetscape way back in 1994. Node.js however is the first implementation to gain any real traction, and it provides some unique benefits, compared to traditional lanfuages. Node now plays critical role in the technology stack of (many high profile companies)https://www.netguru.com/blog/top-companies-used-nodejs-production]. Let's have a look at what those benefits are. 

### The Node.js Execution Model

In very simplistic terms, when you connect to a traditional server, such as Apache , it will spawn a new thread to handle the request. In a language sus as PHP or Ruby, any subsequent I/0 operations for example interacting with a database block the execution of your code until the operation has completed. That is the server has to wait for the database lookup to complete before it can move on to processing the result. If new requests come in while  this happending, the server will spawn new threads to deal with them. This is potentially inefficient, as a large number of thread can cause a system to become sluggish and in the worse cae, for the site to go down. The most common way to support more connections is to add more servers.

Node.js however, is single-threaded. It's also *event-driven*, which means that everything that happens in Node is in reaction to an event. For example, when a new request comes in (on kind of event) the server will start processing it.If it then encounters a blocking I/0 operation, instead of waiting for this to complete, it will register a callback before continiuiing to process the next event. When the I/O operation has finished (anohter kind of event), the server wille xecute the callback and continue working on the original request. Under the hood, Node uses the [libuv](https://github.com/libuv/libuv) library to implement this asynchronous (that is non-blocking) behaviour.

Node's execution model causes the server very little overhead, and consequentlty it's capable of handling a large number of simultaneous connections. The traditional approach to scaling a Node app is to clone it and have the cloned instance share the workload. Node.js even has a *built in module* to help you implement a cloning stategy on a single server.

The following image depicts Nodes execution model:

![Image](https://uploads.sitepoint.com/wp-content/uploads/2012/10/1516152673node_event_loop.png)

## Downsides of NODE

The fact that Node runs in a single thread does impose some limitations. For example, blocking I/O calls should be avoided, CPU-intensive operations should be handed off to a worker thread, and errors should always be handled correctly for fear of crashing the entire process.

[More On This Site](https://www.sitepoint.com/an-introduction-to-node-js/)