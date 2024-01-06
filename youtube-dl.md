[Back to Cheatsheets Index](README.md)
# youtube-dl Cheatsheet

_Note: this cheatsheet is for `yt-dlp`, a fork of `youtube-dl` which fixes a number of issues I have with the orgional_
_Note: `ffmpeg` must be installed for many commands to work to allow for combining separately downloaded video and audio streams._
_Note: this is primarily for downloading from YouTube but it also works for plenty of other platforms._

#### Download best quality format of a video
`yt-dlp <VIDEO-URL>`
_Note: default best quality on YouTube is almost always a webm which limits reuse_

#### Download all videos from a channel in best quality format
`yt-dlp <CHANNEL-URL>`
_Note: default best quality on YouTube is almost always a webm which limits reuse_

#### List available quality formats
`yt-dlp -F <VIDEO-URL>`

#### Download specific quality format
`yt-dlp -f 18 <VIDEO-URL>`

#### Download and combine two specific quality formats
`yt-dlp -f 137+140 <VIDEO-URL>`

#### Download highest quality mp3 audio from video and use thumbnail as album art and embed metadata
`yt-dlp --extract-audio --add-metadata --xattrs --embed-thumbnail --audio-quality 0 --audio-format mp3 <VIDEO-URL>`
_Note: this is useful for musical works not available for purchase/download due to either platform exclusivity, region blocking, DRM or the passing of the artist, however in those situations always seek an alternative way to support the creators._

#### Download best quality format of video and embed en subtitles
`yt-dlp --write-subs en <VIDEO-URL>`
_Note: default best quality on YouTube is almost always a webm which limits reuse_
_Note: subtitle language may not always be consistent eg. `en`, `en-us`, `english`_
