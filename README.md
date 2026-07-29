# Software Developer Guide for Everyday Solutions

## Compressing Videos Using Your Own Computer

### Using FFmpeg
- Use the command below to compress videos. (Useful if you are uploading high-resolution videos on a customer website).
- Run it inside the directory that includes the video, and the output file will be created in the same directory.

I have tried this command on my MacBook and it worked well.

```
ffmpeg -i input.mp4 -c:v libx265 -crf 28 -preset medium -c:a aac -b:a 128k output.mp4
```

Let's break down what the command above does:
- `-i input.mp4`: Specifies your input file.
- `-c:v libx265`: Uses the **H.265/HEVC** video codec, which can offer about **25–50% better compression** than H.264 for the same quality, especially at higher resolutions like 1080p and 4K.
- `-crf 28`: The **Constant Rate Factor** controls quality. A lower number means higher quality and a larger file. The default is 28 for H.265, which provides a reasonable quality for a much smaller file.  For a higher quality output, you could try a value like 23 or 24.
- `-preset medium`: This setting balances encoding speed and compression efficiency. `slow` will give you a smaller file for the same quality but will take longer to process; `fast` will be quicker but result in a larger file.
- `-c:a aac -b:a 128k`: Encodes the audio using the AAC codec at a bitrate of 128 kbit/s, ensuring good audio quality without a large file size.