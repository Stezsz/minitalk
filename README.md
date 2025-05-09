# minitalk – 42 School Project

`minitalk` is a project that involves creating a simple client-server communication protocol using Unix signals.
The goal is to send messages (strings) from a client program to a server program **bit by bit**, using only `SIGUSR1` and `SIGUSR2` signals.

---

## Main Objectives

- Learn inter-process communication using Unix signals.
- Implement a communication protocol to send strings from one process to another.
- Handle message transmission **bitwise**, one character at a time.
- Understand signal handling and asynchronous behavior in Unix-like systems.

---

## Project Structure

### 🔹 Server

- Initializes and prints its **PID** (process ID).
- Waits for incoming signals from a client.
- Reconstructs the message bit by bit and prints it to the terminal.

### 🔹 Client

- Takes two arguments: the server PID and the message to send.
- Sends each character of the string bit by bit using `SIGUSR1` (bit = 0) and `SIGUSR2` (bit = 1).
- Sends a null character (`'\0'`) at the end to indicate the end of transmission.

---

## Technical Requirements

- Only the following functions are allowed: `write`, `malloc`, `free`, `kill`, `getpid`, `signal`, and `pause`.
- Must handle signals asynchronously.
- Must implement both the client and the server.
- Code must follow the **42 Norm (Norminette)**.
- A working `Makefile` must be provided.

---

## Example Usage

```bash
# In one terminal, run the server:
$ ./server
Server PID: 12345

# In another terminal, run the client with the server PID and a message:
$ ./client 12345 "Hello, world!"
```

The server should then print:
```
Hello, world!
```

---

## Conclusion

`minitalk` is a fun and challenging introduction to low-level inter-process communication.
It strengthens your understanding of signals, bit manipulation, and process behavior in Unix systems — key topics in systems programming.

---

> ✅ **Final Grade: 115/100**
> Project made at [42 Lisboa](https://www.42lisboa.com/pt/)
> 👤 Author: Stephan Rodrigues Lassaponari ([@Stezsz](https://github.com/Stezsz))
