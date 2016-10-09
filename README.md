


# Install

1. brew install ffmpeg --with-libquvi --with-libvorbis --with-libvpx
2. Install Apache
3. Test "localhost" in your browser.
4. Configure IP camera to broadcast an RTSP stream. Obtain the URL.
5. Test the RTSP URL stream.
6. Move the FFSERVER configuration file to /etc/
7. Run the Media Server:
```ffserver -f /etc/ffserver.conf```
8. Obtain the RTSP Stream and Save it to the Feed.FFM File
```ffmpeg -v debug -i rtsp://<RTSP_IP_ADDRESS>:<PORT> -c:v copy  http://localhost:8090/feed.ffm```
9. Overwrite Apache's "index.html" with the "index.html" from this repository.
10. Navigate your browser to '''http://localhost:8090/status.html''' to see the status of the data coming from your IP camera to the media server.
11. If data is being received, go ahead and navigate to "localhost". Check your video feed.
