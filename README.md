# AVI Player

A simple AVI player for Arduino IDE.

## conversion

### Cinepak

```sh
ffmpeg -i input.mp4 -c:a mp3 -c:v cinepak -q:v 10 -vf "fps=15,scale=-1:240:flags=lanczos,crop=320:240:(in_w-320)/2:0" AviMp3Cinepak240p15fps.avi

ffmpeg -i input.mp4 -c:a mp3 -c:v cinepak -q:v 10 -vf "fps=30,scale=-1:240:flags=lanczos,crop=320:240:(in_w-320)/2:0" AviMp3Cinepak240p30fps.avi

ffmpeg -i input.mkv -c:a mp3 -c:v cinepak -q:v 20 -vf "fps=15,scale=-1:480:flags=lanczos,crop=800:480:(in_w-800)/2:0" AviMp3Cinepak480p15fps.avi

ffmpeg -i input.mp4 -c:a mp3 -c:v cinepak -q:v 20 -vf "fps=30,scale=-1:480:flags=lanczos,crop=800:480:(in_w-800)/2:0" AviMp3Cinepak480p30fps.avi

ffmpeg -i input.mp4 -c:a mp3 -c:v cinepak -q:v 20 -vf "fps=10,scale=800:-1:flags=lanczos,crop=800:400:0:(in_h-400)/2" AviMp3Cinepak400p10fps.avi
```

### Cinepak color screen for debug only

```sh
ffmpeg -f lavfi -i color=red:320x240:d=3,format=rgb24 -c:v cinepak -q:v 10 -vf "fps=15" red.avi

ffmpeg -f lavfi -i color=green:320x240:d=3,format=rgb24 -c:v cinepak -q:v 10 -vf "fps=15" green.avi

ffmpeg -f lavfi -i color=blue:320x240:d=3,format=rgb24 -c:v cinepak -q:v 10 -vf "fps=15" blue.avi

ffmpeg -f lavfi -i color=white:320x240:d=3,format=rgb24 -c:v cinepak -q:v 10 -vf "fps=15" white.avi
```

### MJPEG

```sh
ffmpeg -i input.mp4 -c:a mp3 -c:v mjpeg -q:v 10 -vf "fps=10,scale=-1:320:flags=lanczos,crop=480:320:(in_w-480)/2:0" AviMp3Mjpeg320p10fps.avi

ffmpeg -i input.mp4 -ac 1 -c:a pcm_u8 -c:v mjpeg -q:v 10 -vf "fps=15,scale=-1:240:flags=lanczos,crop=320:240:(in_w-320)/2:0" AviPcmu8Mjpeg240p15fps.avi

ffmpeg -i input.mp4 -ac 1 -c:a pcm_u8 -c:v mjpeg -q:v 10 -vf "fps=10,scale=-1:320:flags=lanczos,crop=480:320:(in_w-480)/2:0" AviPcmu8Mjpeg320p10fps.avi
```

### my attempts

ffmpeg -i honda.mp4 -c:a mp3 -c:v cinepak -q:v 10 -vf "fps=15,scale=-1:240:flags=lanczos,crop=320:170:(in_w-320)/2:0" HondaAviMp3Cinepak240p15fps.avi

ffmpeg -display_rotation 270 -i honda.mp4 -c:a mp3 -c:v cinepak -q:v 10 -vf "fps=15,scale=168:320:flags=lanczos,crop=168:320:(in_w-168)/2:0" HondaAviMp3Cinepak240p15fps.avi

ffmpeg -i honda_scale.mp4 -c:a mp3 -c:v cinepak -q:v 10 -vf "fps=15,scale=168:88:flags=lanczos" HondaAviMp3Cinepak168p15fps.avi

ffmpeg -i honda_rotate.mp4 -c:a mp3 -c:v cinepak -q:v 10 -vf "fps=15" HondaRotateAviMp3Cinepak168p15fps.avi

ffmpeg -i TinyCashback.mp4 -ss 20:33.00 -to 27:10.00 -c:a mp3 -c:v cinepak -q:v 10 -vf "fps=30" TinyCashbackClip.avi



### AMOLED	(N.B. - second dimension MUST be divisible by 4)

ffmpeg -i NataliaAndreevaAmoled.mp4 -c:a mp3 -c:v cinepak -q:v 11 -vf "fps=30" NataliaAndreevaAmoled.avi

ffmpeg -i input/reddit01.mp4 -c:a mp3 -c:v cinepak -q:v 11 -vf "fps=30" output/reddit01.avi

ffmpeg -i input\S3reddit06.mp4 -c:a mp3 -c:v cinepak -q:v 11 -vf "fps=30" output\S3reddit06.avi

### no audio

ffmpeg -i input/reddit04.mp4 -c:v cinepak -q:v 11 -vf "fps=15" output/reddit04.avi
