# ffmpeg-cheatsheet

#### Encode folder of JPGs into M-JPEG stream in mp4 container in native color space
`ffmpeg -framerate 15 -pattern_type glob -i '*.jpg' output.mp4`

#### Transcode with 1mbps quality target H.264 in YUV 4:2:0 colorspace
`ffmpeg -i output.mp4 -b 1000000 -vf format=yuv420p output_1mbps.mp4`
