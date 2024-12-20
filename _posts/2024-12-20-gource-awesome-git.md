---
title: Gource - awesome git visualization tool 📊
date: 2024-12-20 22:00:00+0100
categories: [tools]
tags: [gource, git, visualization, tools]
---

## What is gource?

[Gource](https://gource.io/) is a tool that visualizes git repositories as video. It's a great way to show the history of the repository in fancy way.

## Installation

I use it on windows, so it's very straightforward to install just simple download installed from main page [https://gource.io/](https://gource.io/).

## Usage

To make it works you need some repository to visualize for example [react](https://github.com/facebook/react).  
In repository directory run:

```ps
gource -1920x1080 --seconds-per-day 1 --auto-skip-seconds 1 --fixed-user-size --colour-images --start-date '2024-01-01' --stop-date '2024-03-01' --camera-mode overview --padding 1.3 --frameless --bloom-multiplier 0.3 --hide mouse,progress,filenames,dirnames --output-ppm-stream ./out.ppm --output-framerate 60
```

### Some mentioned options

- `--auto-skip-seconds 1` - if nothing is happening for 1 second, skip to next change
- `--fixed-user-size` - same size for all users looks better
- `--bloom-multiplier 0.3` - when there is a lot of changes you might want to reduce bloom effect
- `--hide mouse,progress,filenames,dirnames` - hide most of not needed elements
- `--camera-mode overview` - overview mode is better to see what happens overall


## I have out.ppm file, what now?
Now we need to convert it to video file itself has around 32 GB size! 🤯  
So we need to use ffmpeg to do that.

First we need to install ffmpeg from [https://ffmpeg.org/](https://ffmpeg.org/) I chose to use winget.

```ps
winget install "FFmpeg (Essentials Build)"
```

Now we can convert ppm file to video.
```ps
ffmpeg -y -r 60 -f image2pipe -vcodec ppm -i out.ppm -vcodec libx264 -preset medium -crf 18 -pix_fmt yuv420p gource_video.mp4
``` 

Effect is available under [https://youtu.be/viZiY6FqUrY](https://youtu.be/viZiY6FqUrY) 🎥

