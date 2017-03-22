## Client Hello

### Introduction
Before the client will send any position packets, it sends a "HELLO" packet and waits until the server sends back the "hello-OK". This is covered in the "Server" section.

### Contents
It's always helpful to know what is inside the packet. In the case of the HELLO packet, however, there isn't really that much interesting stuff.

Regardless, here's a small table of what's inside.

| Value Name | Byte Range     |
| :------------- | :------------- |
| Persona ID       | Bytes 8-11 (indexes 7-10)       |
| Cryptoticket Bytes       | Bytes 4-7 (indexes 3-6)       |
As you can see, there really isn't much in there.
