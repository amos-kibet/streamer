## HTTP Live Streaming

It is a media streaming protocol for delivering visual and audio media to viewers over the internet.

Launched by Apple in 2009. Before then, `Quicktime Streaming Server` was the de-facto media streaming standard.

### Basic Workflow of Livestreaming ove HLS

- Capturing devices (camera, microphones, etc) capture the content.

- Content is sent to a live video recorder from the capturing device.

- The encoder transmits the content to the video hosting platform via `RTMP`.

- The video hosting platform uses `HLS ingest` to transmit the content to an `HTML5 video player`.

The above process requires two main software solutions: a live video `HLS encoder` and a powerfull `video hosting platform`

HLS uses the same protocol that the web runs on, letting you deploy content using ordinary web servers and content delivery networks. It’s designed to offer reliability and dynamically adapt to network conditions through playback speed optimization for wired and wireless connections.

### How it works

- First, HLS chops up MP4 video content into short (10-second) chunks with `.ts` file extension (MPEG2 Transport Stream).

- Next, an HTTP server stores those streams, and HTTP delivers these short clips to viewers on their devices.

- HLS will play video encoded with the `H.264` or `HEVC/H.265` codecs.

- The HTTP server also creates an [M3U8 playlist file](https://www.dacast.com/support/knowledgebase/how-to-create-an-m3u8-media-link-walkthrough/) (e.g., manifest file) that serves as an index for the video chunks.

With this protocol, a given user’s video player software (like an HTML5 video player) detects deteriorating or improving network conditions. If either occurs, the player software first reads the main index playlist and determines which quality video is ideal.

Then the software reads the quality-specific index file to determine which chunk of video corresponds to the point at which the viewer is watching.

Though `HLS` is compatible with most devices and firewalls, there is a lag time range of around 15-30 seconds. You can improve latency using other software on top of `HLS`, like [Low-Latency](https://www.dacast.com/blog/best-low-latency-video-streaming-solution/) `CMAF for DASH`. This protocol works with the content delivery network and HTML5 video player to carry the weight where HLS streaming is lacking.

`HLS` is highly scalable for delivering live streams and video content across global content delivery networks (CDNs) using ordinary web servers. CDNs share the workload across a network of servers to accommodate a spike in viewership and larger-than-expected live audiences.

CDNs also cache video and audio segments to help deliver a high-quality video streaming experience and improve the viewer experience.

Other benefits of HLS streaming include ad insertion through the VPAID and VAST interfaces, cross-device compatibility, and piracy protection with extensive support for DRM technologies.

### Other Streaming Protocols

1. **Adobe HTTP Dynamic Flash Streaming (HDS)**

2. **Real-Time Messaging Protocol (RTMP)**

3. **Microsoft Smooth Streaming (MSS)**

4. **Dynamic Adaptive Streaming over HTTP (MPEG-DASH)**. Newer protocol, almost similar features to HLS, only that it not compatible with a lot of devices. It is an international standard, while HLS is not.

5. **Real-Time Streaming Protocol (RTSP)**. Has extremely low latency, but has some limitations. It is mostly used to manage and control live streams, rather than transmitting the content. MOstly used in CCTV. Because of its low streaming latency, RTSP requires a constant and stable network connection. Unstable networks will result in dropped frames, macro blocking, and other visual artifacts. Android and iOS devices also don’t have RTSP-compatible players, hence rarely used.

6. **Web Real-Time Communication (WebRTC)**. It is a free, open-source technology released by Google and Ericsson in 2011 to enable real-time video, audio, and data communication without plugins. It’s used to allow real-time video and audio communication inside web pages.

7. **Secure Reliable Protocol**. It’s an open-source technology that aims to minimize the effects of jitter, bandwidth changes, and packet loss to optimize the streaming experience. It is considered the future of livestreaming due to its security, reliability, and low latency streaming.

If you want to be on the cutting edge of video streaming protocols, consider adapting SRT. It is considered the future of streaming alongside HLS, WebRTC, and MPEG-DASH. SRT makes it easy to traverse firewalls without needing help, and it’s economical to deploy over the existing network infrastructure.

Among the above protocols, the most widely used alternative to `HLS` is `MPEG-DASH`. Both use `TCP` over `HTTP`.

However, several key differences distinguish the two protocols:

- **Encoding formats**: `MPEG-DASH` allows the use of any encoding standards, while `HLS` requires the use `H.264 or H.265`

- **Device support**: `HLS` is the only format supported by Apple devices.

- **Segment length**:Default is 6s fro `HLS`, but it can be adjusted. For `MPEG-DASH`, it ranges between 2-10s, although the optimum length is 2-4s.

- **Standardization**: `MPEG-DASH` is an international standard, `HLS` is not.
