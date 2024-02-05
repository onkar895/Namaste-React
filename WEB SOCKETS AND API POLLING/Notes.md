# Live Comments in YouTube Project :

To enable live comments in your application, the initial challenge involves ensuring that the data updates in real-time.

-   This entails tackling two key aspects:
    Obtaining live data and subsequently updating the displayed information on the page. Let's begin by discussing the acquisition of live data, which can be accomplished in two primary ways.

    -   Web Sockets: Web Sockets establish a two-way connection between the server and the user interface (UI), akin to a handshake. Once this connection is established, data can swiftly flow in both directions. This bidirectional communication allows for seamless transmission of data from the UI to the backend and vice versa.

### Example :

Imagine you're having a phone conversation with a friend. Both of you can talk and listen at the same time, right? That's like a web socket - it's a two-way connection.
In technical terms, it's like a special type of phone call between your web browser (UI) and a server. Once this connection is made, both sides can send messages back and forth instantly, just like chatting in real-time.
This allows your application to react quickly to any changes because it's constantly listening for updates from the server, and it can also send messages to the server whenever needed.

-   API Polling:

The second approach is API Polling: In this method, the user interface (UI) periodically sends requests to the server to fetch updates. The server responds to these requests by sending the latest data back to the UI. Unlike Web Sockets, API polling involves one-directional communication, with the UI initiating the request and the server responding accordingly.

### Example :

Now, think of API polling like sending text messages. You send a message (request) to your friend asking what's new, and then you wait for their reply (response).
Similarly, in API polling, your UI sends a request to the server asking for updates. The server then responds with the latest information.
However, unlike web sockets where you can have a continuous conversation, with API polling, you have to keep asking for updates regularly. It's like repeatedly checking your phone for new messages instead of having a live conversation.
This method works well too, but it might not be as fast or efficient as web sockets because there's a delay between each request and response.
So, in simple terms, web sockets allow for real-time, two-way communication like a phone call, while API polling involves sending requests and receiving responses, similar to exchanging text messages.
