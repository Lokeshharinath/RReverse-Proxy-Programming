This contains a simple implementation of a Reverse Proxy Programming in Python.The proxy server facilitates communication between a UDP client and multiple UDP servers
,known as upstream servers. It forwards UDP packets from the client to one of the upstream servers and relays the responses back to the client.

Components

1. client.py
This script represents a UDP client that sends "PING" messages to the proxy server and expects "PONG" responses.It takes two command-line arguments:

--port <port>: Specifies the port number on which the proxy server is listening.
2. server.py
The server.py script simulates a UDP server that responds to "PING" messages with "PONG" messages.
It operates on a specified port and randomly drops packets with a 30% probability to emulate packet loss.

3. proxy.py
The proxy.py script acts as an intermediary between the client and multiple upstream servers.
It forwards incoming "PING" messages from the client to one of the specified upstream servers in a round-robin manner.
The proxy server requires command-line arguments:

--port <proxy_port>: Specifies the port number on which the proxy server listens for incoming requests.
--upstreams <port1> <port2> ...: Specifies the port numbers of the upstream servers.

Usage

Running the Proxy Server
python proxy.py --port <proxy_port> --upstreams <port1> <port2> ...
<proxy_port>: Port number for the proxy server to listen on.
<port1> <port2> ...: Port numbers of the upstream servers.
Running the Client

python client.py --port <proxy_port>
<proxy_port>: Port number the proxy server is listening on.
Running the Server

python server.py --port <port>
<port>: Port number the server is listening on.

Author

Name: Gonthina Lokesh Harinath
Student ID: 11702591
