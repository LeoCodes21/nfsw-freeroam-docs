## Player Info Packet

### Introduction
This packet contains **player information**, including (but not necessarily limited to), the ID and name of the persona (the client that is sending the packet.)

### Contents
So far, we only know where the persona ID and name are. We are not sure if there is more information. Here is a table.

| Value Name     | Byte Range     |
| :------------- | :------------- |
| Persona ID     | Indexes 43-46  |
| Persona Name   | Indexes 4-17   |

Take this data for example:
```
01:41:00:44:45:42:55:47:32:00:00:00:00:00:00:00:00:00:00:00:00:00:
00:00:00:00:00:00:00:00:00:00:00:00:00:04:00:00:00:00:00:00:00:67:
00:00:00:00:00:00:00:b0:79:e6:cf:ee:1e:9c:fb:f5:c5:
cb:e0:00:00:00:00
```
The player name comes immediately after `01:41:00`. Since the name is stored in indexes 4-17, the hex text is this: `45:42:55:47:32:00:00:00:00:00:00:00:00:`
Now, if we convert everything before the first `:00` to text, we get `DEBUG2`. That's the persona name.

The persona ID is surrounded by a bunch of `:00`s... here is the hex text: `67:00:00:00`
If we take _that_, and make it into an integer, we get `103`. That is `DEBUG2`'s persona ID.
