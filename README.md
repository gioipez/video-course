# video-course


## What is video?

[Video](https://en.wikipedia.org/wiki/Video) is the sequence of still images (frames) in a given time. When you pass 24 still images or more in 1 second, your brain will take that as a video, so in summary video is a sequence of still images that causes our brain to think we have a moving scene. [Source](https://github.com/leandromoreira/ffmpeg-libav-tutorial)

## Detailed video compression process

Video transcoding process takes an input file, demultiplex (split) encoded data packets of the elementary streams (video, audio, and/or data), pass them to the decoder to get the raw video/ PCM audio to them process for filtering, resizing, or any other process. Finally the frame are passed to the encoder block which encodes them and generates the output. 

<img src="https://github.com/GioLopez/video-course/blob/main/Images/Transcoding_process_01.png" width="40%" height="50%">

Source: [ffmpeg detailed description](https://ffmpeg.org/ffmpeg.html#toc-Detailed-description)


## Codecs and compression

Typically video is shotted with professionals cameras that are able to generate big amount of frames per seconds in a high resolution, the result of that process is a big asset of a big file that contain in a given period all those frames. The main purpose of video recording is sharing with someone else to entertain, educate, train, or others via different devices, generally those devices doesn't count with enough [bandwidth](https://en.wikipedia.org/wiki/Bandwidth_(computing)) to receive large amount of data per second, that's why compress that information is really important, and there is where codecs plays a big role.

Compression is the process of take a given input (can be a message, video, audio, files, etc) and transmit its content with less information, saving resources while transporting it. Depending on the application, this can support package loss or not, for example a document can not support missing package because it's part of the nature of it, but images, video or audio can live with that. We need to keep in mind as much as we compress, the quality will be lose [[1](https://github.com/GioLopez/video-course#sources)].


When doing video compression it's really important keep a tradeoff between video resolution and bitrate, in the following example we have a comparison of a screenshot from an original video and the same video, with the same resolution with lower bitrate, from 10 Mbps was reduced to 0.5 Mbps.

original    vs     0.5M bitrate

<img src="https://github.com/GioLopez/video-course/blob/main/Images/Bitrate-Original_01.png" width="40%" height="40%">
<img src="https://github.com/GioLopez/video-course/blob/main/Images/Bitrate-1m_01.png" width="40%" height="40%">

In conclusion we are trying to make fit a big picture of big resolution on a "small tube", so the correct way of doing this is to increase the bitrate or decrease the video resolution.

## Configuration parameters

### Resolution / Frame size

It's the size of the images / frames that is passed per second, the usual resolutions can be found on this [List of common resolutions](https://en.wikipedia.org/wiki/List_of_common_resolutions)

Resolution usages between 2009 and 2022

<img src="https://github.com/GioLopez/video-course/blob/main/Images/Screen_resolutions_between_2009_and_2022.png" width="40%" height="40%">

[Screen Resolution Stats Worldwide](https://gs.statcounter.com/screen-resolution-stats#monthly-200903-202206)


### Aspect ratio

[Video](https://en.wikipedia.org/wiki/List_of_common_resolutions) not only has resolution, it has other components:
- Pixel Aspect Ratio (PAR): This is the size of each pixel, the minimum unit in a frame.
- Storage Aspect Ratio (SAR): 
- Display Aspect Ratio (DAR): it's the multiplication of Pixel Aspect Ration and Storage Aspect Ratio. `DAR=PARxSAR`.


By convention 4:3 (DAR) videos has a [PAR](http://www.arielnet.com/pages/show/adi-gba-01323/pixel-aspect-ratio#:~:text=D1%20has%20a%20screen%20resolution,Mac%20OS%20and%20Windows%20systems.) of `10:11 = 0.9090`, normally resolution of 720 x 480 (NTSC) or 720 x 576 (PAL). Wider screen resolutions as 16:9 DAR has a PAR of `40:33 = 1.2121`.

Based on that, we have the following example:

<img src="https://github.com/GioLopez/video-course/blob/main/Images/video_out_from_1610_video.png" width="40%" height="40%">

This is the output of `ffprobe` command run on a transcoded asset

Resolution is `1920x1080`, `SAR=9/10` and `DAR=8/5`

>NOTE: for `FFMPEG` SAR (Sample Aspect Ratio) and PAR (Pixel Aspect Ratio) are the same. 

So for this specific video, that has resolution of `1080p`, the DAR is

    DAR=PAR*(width/height)

    DAR=PAR*width/height

    DAR=1728/1080

So that means this video with resolution of `1920x1080` will be shown in a display of `1728x1080`.

Quicktime inspector show this same information

<img src="https://github.com/GioLopez/video-course/blob/main/Images/quicktime_inspector_video_out_from_1610_video.png" width="40%" height="40%">

### Framerate

### Framerate types

## Bitrate


## Common video operation

### Transcoding

### Transmuxing

### Transrating

### Transsizing



## Audio encoding

## Sample rate


## Deinterlacing


## Sources

1. I'm following a structure similar to the one [Jan Ozer](https://www.linkedin.com/in/jan-ozer/) used on his course at [Udemy](https://www.udemy.com/course/compressing-video-for-web-disc-and-pctvconsole-playback/).
2. [List of common resolutions](https://en.wikipedia.org/wiki/List_of_common_resolutions).
3. [Pixel Aspect Ratio](http://www.arielnet.com/pages/show/adi-gba-01323/pixel-aspect-ratio#:~:text=D1%20has%20a%20screen%20resolution,Mac%20OS%20and%20Windows%20systems.)