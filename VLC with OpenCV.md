# Recieve VLC Streaming(RTSP) with OpenCV 3.4

### installation

1. OpenCV 3.4

    : [reference](https://github.com/SangA-Lee/INSTALLATION/blob/main/Opencv%203.4.md)

2. VLC 

    : [download VLC](https://www.videolan.org/vlc/download-windows.ko.html)
    
### 1st try

        cv::VideoCapture capture(rtsp_url, cv::CAP_FFMPEG);
        
> [rtsp @ 0000018067cc24a0] method SETUP failed: 461 Client error

### 2nd try

set Environment Variable 

                  [variable]          |       [value]
        OPENCV_FFMPEG_CAPTURE_OPTIONS | rtsp_transport;udp

and then

        cv::VideoCapture capture(rtsp_url, cv::CAP_FFMPEG);

> [h264 @ 0000019c8126ada0] Missing reference picture, default is 0  
> [h264 @ 0000025d8fcea860] co located POCs unavailable  
> [h264 @ 0000025d8fcfd140] mmco: unref short failure  
> [h264 @ 0000025d8f8e0a20] error while decoding MB 43 11, bytestream -5  
> [h264 @ 0000019d8f2742a0] reference picture missing during reorder

### 3rd try

OpenCV build with GStreamer


    
