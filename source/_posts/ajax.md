---
title: ajax
date: 2018-01-12 20:56:47
tags:
---



- wiki https://en.wikipedia.org/wiki/Ajax\_(programming)


    Ajax (also AJAX; /ˈeɪdʒæks/; short for "Asynchronous JavaScript And XML")[1] is a set of Web development techniques using many Web technologies on the client side to create asynchronous Web applications. With Ajax, Web applications can send and retrieve data from a server asynchronously (in the background) without interfering with the display and behavior of the existing page. By decoupling the data interchange layer from the presentation layer, Ajax allows for Web pages, and by extension Web applications, to change content dynamically without the need to reload the entire page.[2] In practice, modern implementations commonly substitute JSON for XML due to the advantages of JSON being native to JavaScript.[3]

    Asynchronous HTML and HTTP (AHAH) involves using XMLHTTPRequest to retrieve (X)HTML fragments, which are then inserted directly into the Web page.

##### 缺点
- ajax在低级设备上不被支持,这样代码必须在简单的form表单可以运行
- same-origin policy 不支持跨域调用,但是也可以通过iframe或者JSONP技术来绕开这个限制.
- The asynchronous callback-style of programming ,难以调试
- 异步这个性质会导致client must poll the server, instead of listening, which incurs significant overhead. 低效, websockets可以作为一种替代方案

##### 相关名词
- JSONP
    - https://en.wikipedia.org/wiki/JSONP#JSONP


    JSONP (JSON with Padding or JSON-P[1]) is used to request data from a server residing in a different domain than the client. It was proposed by Bob Ippolito in 2005.[2] JSONP enables sharing of data bypassing same-origin policy. The policy disallows running JavaScript to read media DOM elements or XHR data fetched from outside the page's origin. The aggregation of the site's scheme, port number and host name identifies as its origin. Due to inherent insecurities, JSONP is being replaced by CORS.

- callback


    In computer programming, a callback is any executable code that is passed as an argument to other code, which is expected to call back (execute) the argument at a given time. This execution may be immediate as in a synchronous callback, or it might happen at a later time as in an asynchronous callback. In all cases, the intention is to specify a function or subroutine as an entity[clarification needed] that is, depending on the language, more or less similar to a variable (see first-class functions).

- First-class function


- poll
    - 轮询


    Polling is the process where the computer or controlling device waits for an external device to check for its readiness or state, often with low-level hardware. For example, when a printer is connected via a parallel port, the computer waits until the printer has received the next character. These processes can be as minute as only reading one bit. Τhis is sometimes used synonymously with busy-wait polling. In this situation, when an I/O operation is required, the computer does nothing other than check the status of the I/O device until it is ready, at which point the device is accessed. In other words, the computer waits until the device is ready. Polling also refers to the situation where a device is repeatedly checked for readiness, and if it is not, the computer returns to a different task. Although not as wasteful of CPU cycles as busy waiting, this is generally not as efficient as the alternative to polling, interrupt-driven I/O.

    Polling, or polled operation, in computer science, refers to actively sampling the status of an external device by a client program as a synchronous activity. Polling is most often used in terms of input/output (I/O), and is also referred to as polled I/O or software-driven I/O.

- Parallel port
    - https://en.wikipedia.org/wiki/Parallel_port#Centronics
    - 主要由打印机技术发展而开发出的技术,host和打印机并行通信,后来hosts发展出了缓冲技术,提高了打印机的效率,降低了通信成本


    A parallel port is a type of interface found on computers (personal and otherwise) for connecting peripherals. The name refers to the way the data is sent; parallel ports send multiple bits of data at once, in parallel communication, as opposed to serial interfaces that send bits one at a time. To do this, parallel ports require multiple data lines in their cables and port connectors, and tend to be larger than contemporary serial ports which only require one data line.

- WebSocket


    WebSocket is a computer communications protocol, providing full-duplex communication channels over a single TCP connection. The WebSocket protocol was standardized by the IETF as RFC 6455 in 2011, and the WebSocket API in Web IDL is being standardized by the W3C.
    WebSocket is a different TCP protocol from HTTP. Both protocols are located at layer 7 in the OSI model and, as such, depend on TCP at layer 4. Although they are different, RFC 6455 states that WebSocket "is designed to work over HTTP ports 80 and 443 as well as to support HTTP proxies and intermediaries" thus making it compatible with the HTTP protocol. To achieve compatibility, the WebSocket handshake uses the HTTP Upgrade header[1] to change from the HTTP protocol to the WebSocket protocol.
    The WebSocket protocol enables interaction between a browser and a web server with lower overheads, facilitating real-time data transfer from and to the server. This is made possible by providing a standardized way for the server to send content to the browser without being solicited by the client, and allowing for messages to be passed back and forth while keeping the connection open. In this way, a two-way (bi-directional) ongoing conversation can take place between a browser and the server. The communications are done over TCP port number 80 (or 443 in the case of TLS-encrypted connections), which is of benefit for those environments which block non-web Internet connections using a firewall. Similar two-way browser-server communications have been achieved in non-standardized ways using stopgap technologies such as Comet.
    The WebSocket protocol is currently supported in most major browsers including Google Chrome, Microsoft Edge, Internet Explorer, Firefox, Safari and Opera. WebSocket also requires web applications on the server to support it.
