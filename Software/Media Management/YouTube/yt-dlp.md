---
created: 2023-06-28
---

yt-dlp is a a popular fork of [[youtube-dl]].

## Install

```
# Also a good idea to install ffmpeg
# On macOS:
brew install yt-dlp ffmpeg
```

## Basic Usage

```
yt-dlp <video url>
```

### Format/Quality Selection

```
# List all formats available
yt-dlp <video url> -F

# Download a specific video with ID from above command
yt-dlp <video url> -f '<id>'

# Combine audio and video sources
yt-dlp <video url> -f '<id>+<id>'

# Choose best audio and best video
yt-dlp <video url> -f 'bv*+ba'
```

## Resources

- GitHub: https://github.com/yt-dlp/yt-dlp

