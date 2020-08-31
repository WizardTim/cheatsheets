# ffmpeg-cheatsheet

#### Encode folder of JPGs into M-JPEG stream in mp4 container in native color space
`ffmpeg -framerate 15 -pattern_type glob -i '*.jpg' output.mp4`

#### Transcode with 1mbps quality target H.264 in YUV 4:2:0 colorspace
`ffmpeg -i input.mp4 -b 1000000 -vf format=yuv420p output_1mbps.mp4`

#### Trancode with 1mbps quality target with scale x=1920 y=(aspect divisible by 2) (can be flipped for y axis or different modulus)
`ffmpeg -i input.mp4 -b 1000000 -vf scale=1920:-2 output_1mbps.mp4`

#### Combine video & audio streams into mkv file (without transcoding)
`ffmpeg -i video.mp4 -i audio.aac -c copy output.mkv`

#### Increase volume of the audio stream of any container to 150%
`ffmpeg -i input.mp4 -filter:a "volume=1.5" output.mp4`
