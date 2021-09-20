[Back to Cheatsheets Index](README.md)
# youtube-dl Cheatsheet

#### List available quality formats
`youtube-dl -F <URL>`

#### Download specific quality format
`youtube-dl -f 18 <URL>`

#### Download and combine two specific quality formats
`youtube-dl -f 137+140 <URL>`

#### Rip highest quality mp3 audio from video and use thumbnail as album art and transfer metadata
`youtube-dl --extract-audio --add-metadata --xattrs --embed-thumbnail --audio-quality 0 --audio-format mp3 <URL>`
