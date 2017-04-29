## Introduction

Motion JPEG (M-JPEG or MJPEG) is a video compression format in which each video frame or interlaced field of a digital video sequence is 
compressed separately as a JPEG image.The MJPEG video codec is mostly used in IP cameras and cetain digital cameras.

## Advantages of MJPEG

* MJEG video codec produces  higher quality videos compared to codecs based on temporal interframe compression such as H.264.Temporal interface compressions codecs use  sophisticated algorithms to apply compression across the video as a whole discarding data in the process.

* MJPEG is simple to implement as is non-proprietary and the variance from one manufacturer to the next is typically minimal.In comparison H.264 have many variants and its implementation different from one  

* Uses minimum computing power to encode and decode

* It tolerates rapidly changing motion in the video stream, whereas compression schemes using interframe compression can often experience unacceptable quality loss when the video content changes significantly between each frame.


## Disadvantages of MJPEG

* Video produced with MJPEG are often huge in size compared to temporal interframe compression vodecs such as H.264.


## Aim 

This is an attempt to reduce the file size of MJPEG videos without affecting the perceived video quality.

## Methodology

An MJPEG video comprises of  a series of JPEG frames.Firsly we convert a sample high quality lossless image into JPEG images of various qualities with different encoders to determine at which quality there is no perceived quality loss and which decoder produces the smallest JPEG. 

>Butteraugli is a project that estimates the psychovisual similarity of two images. It gives a score for the images that is reliable in the domain of barely noticeable difference.

We need to achieve a butteraugli score of less than one to ensure that the visual quality isn't affected.

![Decoder comparisions](https://i.gyazo.com/10109b35b7d03a4b6a51d0009c30ca8a.png "Decoder comparisions")

Based on the data above , we can conclude that the following:

* Regardless of the jpeg encoder used , quality 95 is the sweet spot where we get great quality with file size saving
* Guetzli generates the smallest JPEG at a given quality
* libjpeg-turbo generates slighly better JPEG than all other decoders.However at a quality setting of 95 its irrelevant as the perceived quality loss is not noticeable for all encoders.




