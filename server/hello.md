## Server Hello

### Introduction
Before the client will send any position packets, it needs a certain packet to be sent by the server. This packet is known as the "hello-OK" packet, since it is only sent after the client sends a [`HELLO`](client/hello.md) packet, and is absolutely necessary for the client to begin sending anything else. If the "hello-OK" is not sent, then the client will continue to send `HELLO` packets until receiving the hello-OK.

### Client Hello Parsing
Not much information is needed from the client->server HELLO packet. The only thing that's really needed is the persona ID.

So, how do we get the persona ID? It is set in 4 bytes of the client HELLO; byte #8, byte #9, byte #10, and byte #11.

(corresponding indexes: 7, 8, 9, 10)

### Contents
Currently we do not know everything that _needs_ to be in the hello-OK. However, we do have an alternative.

First, we create an array of 11 bytes. (In Java, we use a `ByteBuffer`:  `ByteBuffer.allocate(11)`)
The first 2 bytes are `0x00`. The 3rd byte is `0x01`. The next 4 bytes are the 4th, 5th, 6th, and 7th bytes of the client `HELLO`.
The last 4 bytes are all `0x01`.


Unfortunately, this doesn't always work. We are not sure why.
