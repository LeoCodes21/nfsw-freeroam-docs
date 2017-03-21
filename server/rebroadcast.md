## Packet Rebroadcasting

### Introduction
The UDP multiplayer system is not a simple one that simply re-broadcasts whatever the client sends. Instead, packets being sent by the client must be modified on the server's end before re-sending them to the other clients. Thankfully, we already know what to do.

### The Header
The server adds a "header" of 12 bytes to the beginning of each packet. The client also sends a header, but the server seems to end up replacing it. That being said, what exactly is _in_ the header?

Well... let's find out.


The first 2 bytes are what we call **sequence bytes**. Packets have a counter in them, presumably so the client can determine if a packet was lost. The counter is filled into these two bytes.

The next byte is a **fixed byte**, or one that always has the same value. Its value is always `0x02`.

The next 2 bytes are for the **time**. The time is very easy to calculate; all that is needed is the current time in milliseconds and the *session starting time*. (More on this later.)
