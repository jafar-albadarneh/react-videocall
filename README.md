## WebRTC, React and Node Js
This is a demo depicting the use of the best peer-to-peer communication technology, WebRTC. Whether you want to implement some video calls capabilities or even peer-to-peer data transfer, WebRTC is the best option.

As far for my understanding, the technology **`WebRTC`** consists of Three main modules:

<strong> 1- RTCMediaStream </strong>

Responsible for acquiring Audio and Video from the client browser, and preprare them to be streamed either locally or to a remote peer

<strong> 2- RTCPeerConnection </strong>

Responsible for establishing the peer-to-peer connection, by mainly creating and sending a connection offer from a side, and accepting and creating a response from the other side.
This process can hide some complications for cases where peers doesn't have static public IPs used for communication. Ex. 4G Nating (sitting behind a firewall), in such case, their IP won't be reachable as the singnaling process will fail. The solution for this is by using a STUN( `Session Traversal Utilities for NAT` ) server, where they can tell what is your public IP to be used for passing data through. There are a bunch of publicly available STUNs to be used. The list can be found here: [**STUN servers List**](https://gist.github.com/zziuni/3741933). This demo uses google stun server.
For availablity, you can also configure some relay server-side channels, in order to give you high availability in cases the peer-to-peer connection is lost. Such support can be satisfied by counting on some TURN (`Traversal Using Relays around NAT`) servers.

<strong> 3- RTCDataChannel </strong>

Responsible mainly for data sharing. It works exactly like socket data transmission, with two options (reliable using TCP) and  (unreliable using UDP). The Api is very flexible and looks similar to what you used to code in web sockets.

## DEMO
**What is it about**
## React-VideoCall
Demo app: [webrtc-jafaralbadarneh ](https://webrtc-jafaralbadarneh.herokuapp.com/) 

A video call peer-to-peer application over web. Built with `react-js` and `node`. It enables you to establish a video call with anyone with his ID. the application will generate a new unique ID every time you open a new tab.
The application uses `socket.io` to manage handling call notifications, call pickups and hangups.

**Development**

```
# Running the server [port 5000]
yarn watch:server

# Running the client [port 9000]
yarn watch:client
```

**Deployment**

You can deploy a verision of the app on heroku using the following click-to-deploy button:

[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy?template=https://github.com/jafar-albadarneh/react-videocall/tree/master)
