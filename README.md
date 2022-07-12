# video-course

## Codecs and compression

Compression is the process of take a given input (can be a message, video, audio, files, etc) and transmit its content with less information, saving resources while transporting it. Depending on the application, this can support package loss or not, for example a document can not support missing package because it's part of the nature of it, but images, video or audio can live with that. We need to keep in mind as much as we compress, the quality will be lose [[1](https://github.com/GioLopez/video-course#sources)].


When doing video compression it's really important keep a tradeoff between video resolution and bitrate, in the following example we have a comparison of a screenshot from an original video and the same video, with the same resolution with lower bitrate, from 10 Mbps was reduced to 0.5 Mbps.

original    vs     0.5M bitrate

<img src="https://github.com/GioLopez/video-course/blob/main/Images/Bitrate-Original_01.png" width="40%" height="50%">
<img src="https://github.com/GioLopez/video-course/blob/main/Images/Bitrate-1m_01.png" width="40%" height="50%">

In conclusion we are trying to make fit a big picture of big resolution on a "small tube", so the correct way of doing this is to increase the bitrate or decrease the video resolution.

## Bitrate


## Framerate

### Framerate types

## Audio encoding

## Sample rate


## Deinterlacing


## Sources

1. I'm following a structure similar to the one [Jan Ozer](https://www.linkedin.com/in/jan-ozer/) used on his course at [Udemy](https://www.udemy.com/course/compressing-video-for-web-disc-and-pctvconsole-playback/).
2. 