# Proposed Audio Format Standard
As a producer, I want to upload a file so that I can get connection and browser-friendly versions to listeners.


## Input

The accepted input format should be WAV.


## Output

We will use FFMPEG to transcode WAV into a lossless source: FLAC

The .flac file will then be used to create different .mp3 and .m4a output formats:
* 128 kbps MP3 which has the most support
* High Efficiency AAC which has a better sound and can be used on mobile apps
