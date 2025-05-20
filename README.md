# Reflection 

## 2.1 Original code of broadcast chat

![](./2.1.png)

To run the server, we run `cargo run --bin server` and to run the client, we run `cargo run --bin client` 

We have implemented a websocket communication between the server and the client. When any client sends a message, it will be broadcasted to all clients. We can see for each messages sent by a client, the message is broadcasted to all clients.

## 2.2 Modifying port 

`server.rs`
```rust 
let listener = TcpListener::bind("127.0.0.1:8080").await?;
println!("listening on port 8080");
```
We can modify the port by changing the port number at `Server::bind` function in the server code. We also have to change the port number where the client connects to in the `Client::connect` function. 

`server.rs` will listen to the incoming connection to the address, the websocket connection will be initiated by the client. The server will accepts the incoming connections and handles the incoming messages.

