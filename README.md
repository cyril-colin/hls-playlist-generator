# HLS Playlist Generator

Gets accurate HLS segment lengths for a video file by using key frames, then optionally generates an HLS .m3u8 playlist.

### Background
When direct streaming a video via HLS, the segment lengths are determined by the key frames.

In order to generate an accurate playlist, hls-playlist-generator first extracts the key frames using `ffprobe` and uses the target segment length specified to choose the correct segment lengths that `ffmpeg` would use.

## Requirements

[ffprobe](https://ffmpeg.org/ffprobe.html)

## Installation

Use the package manager  to install foobar.

```bash
npm install hls-playlist-generator
```
or for CLI usage
```bash
npm install -g hls-playlist-generator
```

## Usage

```es6
var hpg = require('hls-playlist-generator')

// Write the .m3u8 playlist to the output file
hpg('./path-to/media-file.mkv', './path-to/playlist.m3u8', 3)

// Return an array of segment lengths
hpg('./path-to/media-file.mkv', 3)

// or (target segment length defaults to 3)
hpg('./path-to/media-file.mkv')
```

## CLI Usage

```bash
# Write the .m3u8 playlist to the output file
hls-playlist-generator "C:/Path with spaces/movie.mkv" "./playlist.m3u8" 3

# Return an array of segment lengths
hls-playlist-generator "C:/Path with spaces/movie.mkv" 3

# or (target segment length defaults to 3)
hls-playlist-generator "C:/Path with spaces/movie.mkv"
```

<img src="https://raw.githubusercontent.com/mcoop320/hls-playlist-generator/master/cli_sample.png" />

## License
[MIT](https://choosealicense.com/licenses/mit/)