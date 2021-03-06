This project is to demonstrate how to build a live broadcast app. It include these features:

* create a room to broadcast your live stream
* join a room to watch the live
* send likes and comments

![image](https://cloud.githubusercontent.com/assets/1646564/16791969/658d8e66-48f6-11e6-8329-6e9ef7f43e75.png)


## Introduction

* RTMP server - Nginx RTMP module(https://github.com/arut/nginx-rtmp-module)
* WebSocket server - Socket.io(http://socket.io/)
* iOS client - VideoCore(https://github.com/jgh-/VideoCore) to push stream, IJKPlayer(https://github.com/Bilibili/ijkplayer) to play stream

## How to run

#### 1. Nginx RTMP server

You need to set up your own rtmp server, the guidance can be found here: https://github.com/arut/nginx-rtmp-module


#### 2. WebSocket server

Just go to the `live-server` folder, run `npm install`, then start the server by `node app.js`

#### 3. iOS client

Go the the `live-ios` folder, run `pod install`(must use cocoapods 0.39.0)

In Config.swift, update the server url:
```
struct Config {
    static var rtmpPushUrl = "rtmp://139.196.232.10/live/"
    static var rtmpPlayUrl = "rtmp://139.196.232.10/live/"
    static var serverUrl = "http://172.16.20.24:3000"
}

```

The app can also be run on a simulator, but to broadcast, you need to run it on a real device

