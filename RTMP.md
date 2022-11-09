## Real-Time Messaging Protocol

It is communication technology that enables live video streaming over the internet. It’s based on Transmission Control Protocol (TCP) technology and was originally developed by Macromedia for their Flash Player, which later became Adobe Flash Player after the company was acquired by Adobe.

Its purpose is to deliver content from an encoder to an online video host. This process is called `ingestion`.

It's capable of [low-latency streaming](https://www.dacast.com/blog/best-low-latency-video-streaming-solution/).

Here are some facts about RTMP.

- RTMP is a live streaming protocol that transmits video files from an encoder to an online video hosting platform.

- RTMP and its variations stream on TCP and UDP (User Datagram Protocol).

- RTMP doesn’t stream on HTTP (whereas standards like HLS do).
- RTMP supports audio codecs like AAC and MP3.

- H.264 is a common video codec for RTMP encoding, but it also supports other codecs like x264.

- RTMP ingest supports the use of low-cost encoding tools.

- RTMP has several distinct variations.

- RTMP has been mostly deprecated for general use and is no longer supported by Adobe.

There are three distinct components that make `RTMP` ingest work:

- Handshake: client-server 'shake hands', in order to initiate connection.

- Connection: Once 'handshake' is complete, a connection is made. This involves exchange of data using `AMF` (Action Message Format) encoding. This establishes a communication standard between the client and server, including general specifications for things like video playback, frame dimensions, and bandwidth.

- Stream: Once connection is established, the stream is initiated. This phase allows for essential user commands like play and pause to be executed.

### RTMP Variations

1. [RTMPS](https://www.dacast.com/blog/rtmps-streaming/): Usess ssl certification to generate a more secure streaming.

2. RTMPE: Uses an alternative secure streaming method.

3. RTMPT: Uses tunneling

4. [RTMFP](https://en.wikipedia.org/wiki/Real-Time_Media_Flow_Protocol): Uses UDP.
