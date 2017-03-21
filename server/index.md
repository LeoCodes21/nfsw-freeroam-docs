## Server Protocol

This section is dedicated to the server's part in the free-roam protocol. The server uses a very simple model for creating new packets; for the most part, it simply takes the client's packets and adds a special "header" to them, and then re-broadcasts them to the other connected clients.
