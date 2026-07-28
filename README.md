# Software Developer Guide for Everyday Solutions

## Compressing Videos Using Your Own Computer

- Use the command below to compress videos. (Useful if you are using videos on a customer website). Run it inside the directory that includes the video, and the output file will be created in the same directory.

I have tried this command on my MacBook and it worked well.

```
ffmpeg -i input.mp4 -c:v libx265 -crf 28 -preset medium -c:a aac -b:a 128k output.mp4
```

Let's break down what the command below does:
- `-i input.mp4`: Specifies your input file.