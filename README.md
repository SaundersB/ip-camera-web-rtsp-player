# IP Security Camera System 

Many IP security cameras offer RTSP video feeds for remote viewing. In order to run analytic software and other tools the user must obtain data from the camera in this manner. Additionally, it would be beneficial to view the video feed within a browser instead of using a proprietary piece of software. 

The solution I've provided below allows the user to install FFMPEG, a popular media tool for conversion, and then host the RTSP stream within the browser.



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
12. Add both the media server and RTSP streams to the boot commands of your respective system.




# Troubleshoot

If you're having a problem installing, please PM me and I"ll do my best to help you.
