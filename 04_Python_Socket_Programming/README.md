# Python Socket Programming on Raspberry Pi Zero 2W

## Objective

The objective of this exercise was to understand the fundamentals of network communication using Python sockets on Raspberry Pi Zero 2W.

Topics covered:

- Client-Server Architecture
- Socket Creation
- Socket Connection
- Sending and Receiving Data
- Exception Handling
- Persistent Server using `while True`
- Practical TCP Client-Server Communication

---

# Client-Server Model

A network application generally consists of two components:

## Server

The server:

- Creates a socket
- Binds to an IP address and port
- Waits for incoming client requests
- Processes requests
- Sends responses

## Client

The client:

- Creates a socket
- Connects to the server
- Sends a request
- Waits for a response
- Closes the connection

### Communication Flow

```text
Client
   |
   | Request
   V
Server
   |
   | Response
   V
Client
```

---

# Socket Programming Fundamentals

A socket is an endpoint for communication between two systems over a network.

Python provides the socket module to implement network communication.

```python
import socket
```

---

# Client Socket Programming

## Client Flow

```text
Create Socket
      ↓
Resolve Server Address
      ↓
Connect To Server
      ↓
Send Request
      ↓
Receive Response
      ↓
Close Connection
```

---

## Client Program

```python
import socket
import sys

try:
    mysock = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

except socket.error:
    print("Failed to create socket")
    sys.exit()

try:
    host = socket.gethostbyname("www.google.com")

except socket.gaierror:
    print("Failed to get host")
    sys.exit()

mysock.connect((host, 80))

message = "GET / HTTP/1.1\r\n\r\n"

try:
    mysock.sendall(message.encode())

except socket.error:
    print("Failed to send")
    sys.exit()

data = mysock.recv(1000)

print(data)

mysock.close()
```

---

# Client Functions Explained

## socket()

Creates a TCP socket.

```python
socket.socket(socket.AF_INET, socket.SOCK_STREAM)
```

### Parameters

| Parameter | Meaning |
|-----------|----------|
| AF_INET | IPv4 Addressing |
| SOCK_STREAM | TCP Protocol |

---

## gethostbyname()

Converts a domain name into an IP address.

```python
host = socket.gethostbyname("www.google.com")
```

---

## connect()

Establishes a connection with the server.

```python
mysock.connect((host,80))
```

---

## sendall()

Sends the complete request to the server.

```python
mysock.sendall(message.encode())
```

---

## recv()

Receives data from the server.

```python
data = mysock.recv(1000)
```

The value `1000` specifies the maximum number of bytes to receive.

---

## close()

Terminates the socket connection.

```python
mysock.close()
```

---

# Exception Handling

To make the application robust, exception handling was added using try-except blocks.

## socket.error

Occurs when socket creation or transmission fails.

```python
except socket.error:
```

---

## socket.gaierror

Occurs when DNS lookup fails.

```python
except socket.gaierror:
```

---

# Server Socket Programming

## Server Flow

```text
Create Socket
      ↓
Bind IP Address and Port
      ↓
Listen For Clients
      ↓
Accept Connection
      ↓
Receive Data
      ↓
Send Response
      ↓
Close Connection
```

---

## Server Program

```python
import socket
import sys

mysock = socket.socket(socket.AF_INET,
                       socket.SOCK_STREAM)

try:
    mysock.bind(("",1234))

except socket.error:
    print("Failed to bind")
    sys.exit()

mysock.listen(5)

while True:

    conn, addr = mysock.accept()

    data = conn.recv(1000)

    if not data:
        break

    conn.sendall(data)

conn.close()

mysock.close()
```

---

# Server Functions Explained

## bind()

Associates the socket with a specific port.

```python
mysock.bind(("",1234))
```

### Parameters

| Parameter | Meaning |
|-----------|----------|
| "" | Listen on all network interfaces |
| 1234 | Port Number |

---

## listen()

Places the socket into listening mode.

```python
mysock.listen(5)
```

The number 5 specifies the backlog queue size.

---

## accept()

Waits for incoming client connections.

```python
conn, addr = mysock.accept()
```

Returns:

- Connection Object
- Client Address

---

## recv()

Receives incoming data from the client.

```python
data = conn.recv(1000)
```

---

## sendall()

Sends data back to the client.

```python
conn.sendall(data)
```

This implementation behaves as an Echo Server.

---

# Persistent Server Using while True

To keep the server running continuously:

```python
while True:
```

This allows the server to:

- Handle multiple requests
- Accept new client connections
- Run indefinitely until manually stopped

---

# Practical Exercise: Request Detection Server

As a practical exercise, the server was modified to detect incoming requests.

```python
while True:

    conn, addr = mysock.accept()

    data = conn.recv(1000)

    print("Got a request!")

    if not data:
        break
```

---

# Output

```text
pi@raspberrypi:~$ python3 Server.py

Got a request!
Got a request!
Got a request!
```

This confirms that:

- The server successfully received incoming requests.
- The client successfully connected.
- TCP communication was established.
- Socket programming was functioning correctly on Raspberry Pi Zero 2W.

---

# Key Learnings

- Fundamentals of TCP/IP Communication
- Client-Server Architecture
- Python Socket Programming
- Exception Handling
- TCP Connection Management
- Request and Response Mechanism
- Continuous Server Execution
- Practical Network Programming on Raspberry Pi Zero 2W

---

# Repository Structure

```text
04_Python_Socket_Programming/
│
├── README.md
├── Images/
│   ├── client_program.png
│   ├── server_program.png
│   └── practical_output.png
│
└── Source_Code/
    ├── client.py
    └── server.py
```
