# Original code, and how it run

![alt text](img/image.png)

Open one terminal, start the server:

`cargo run --bin server`

You should see

`listening on port 2000`

Open one or more additional terminals and launch a client in each:

`cargo run --bin client`

Each client will print:

`From server: Welcome to chat! Type a message`

In any client, type a line and hit enter. For example:

`sigma`

The server terminal logs:

`From client 127.0.0.1:XXXXX "sigma"`

All connected clients will print:

`From server: sigma`

Every time someone types, the server broadcasts that message to all subscribers via the broadcast channel, and each client’s select‐loop picks it up and prints it out.


# Modifying port

![alt text](img/image2.png)

Since both sides still agree on port 8080, everything continues to function exactly as before.


# Small changes, add IP and Port

![alt text](img/image3.png)

When you run multiple clients on the same machine, it’s helpful to see at a glance which terminal printed each incoming line. Adding a static prefix makes that obvious.