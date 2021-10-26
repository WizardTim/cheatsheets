[Back to Cheatsheets Index](README.md)
# FFmpeg Cheatsheet

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

#### Apply math function to folder of JPGs, eg. output JPG will be mean of all JPGs in folder (useful for image reducing noise with multiple exposures)
`ffmpeg convert -evaluate-sequence mean '*.jpg' output.jpg`

#### Transcode video to streaming friendly format (recommended by lbry.tv) 
`ffmpeg -i input.mp4 -c:v libx264 -crf 21 -preset faster -pix_fmt yuv420p -maxrate 5000K -bufsize 5000K -vf 'scale=if(gte(iw\,ih)\,min(1920\,iw)\,-2):if(lt(iw\,ih)\,min(1920\,ih)\,-2)' -movflags +faststart -c:a aac -b:a 160k output.mp4`

#### Segment audio file into 5 second file segments
`ffmpeg -i input.mp3 -f segment -segment_time 5 -c copy output%04d.mp3`

#### Save a frame as a PNG every 1 second
`ffmpeg -i input.mp4 -vf fps=1 output%d.png`
