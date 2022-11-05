In a nutshell, streaming starts from streamer's computer, to the streaming servers, to the viewer's device.

### How

- Streamer starts the recording

- Recording is encoded (Open Broadcaster Software). YouTube/Twitch have encoding software that enables browser webcam, phone camera to do livestreaming.

- Protocol used:

  - RTMP (Real TimeMessaging Protocol). It is a TCP-based protocol.
  - SRT (Secure Reliable Transport). It seeks to replace RTMP. UDP-based, low latency. However, it is not yet supported by most streaming platforms

- Streaming service connects the streamer to the nearest Point of Presence (PoP) server, using RTMP/SRT.

- From the streaming platform:
  - nearest PoP is selected,
  - stream is segmented/transcoded, and
  - packaged
- The result is a stream with different quality/resolution which is presented to the viewer depending on the quality of their internet.

- Note: segmentation/transcoding is compute-intensive, this is where the stream is segmented in small junks of different quality, and transcoded to different formats in parallel.

- The result of segmentation/transcoding is then packaged into different formats that the video players can understand. Most common livestreaming formats are HLS (Http LiveStream) & DASH.
  - HLS: Most popular. Consists of a manifest file & small video chunks. The manifest file acts a directory to tell the browser/player where all the video files are & where to load the video chunks.
  - DASH (Dynamic Adapted Streaming over Http).
- The resulting HLS/DASH files are cached & distriuted by CDNs to the viewers devices. Latency here is in the range of a few seconds. To further reduce latency, quality can be sacrificed.

- Some platforms provide a `coarse knob`, which lets the streamer to adjust the quality of the stream.

### TCP vs UDP

- TCP: Reliable (guaranteed delivery), packets arrive in order (sequencing of data), comparatively slow

- UDP: Non-reliable (no guaranteed delivery), no sequenced delivery, comparatively faster.

### Media/Data Transport in WebRTC

- Media Stream: Happens over SRTP (Secure Realtime Protocol), RTP (Realtime Protocol), RTCP (Realtime Control Protocol)

- Data Stream: Happens over DTLS (Dataggram Transport Layer Security), SCTP (Stream Control Transport Protocol)

### Resolution Codecs

- Resolutions: 360p, 720p, 1080p, 4k

- Codecs: ABR, DASH, HLS

### Other Terminologies

- Bitrate Video Streaming

- H.264-formatted standard streaming protocol. Also known as MPEG-4 Part 10 or Advanced Video Coding (MPEG-4 AVC)
