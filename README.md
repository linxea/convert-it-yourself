# Installation

## Simply run the npm script command

Only if you are using MacOS and you have `brew` installed (you really should).

- `npm run download`
- `./ffmpeg`

## Or install [ImageMagick](https://www.imagemagick.org) and [FFmpeg](https://www.ffmpeg.org/) manually

### 1. Install ImageMagick in MacOs through [brew](https://brew.sh/)

- Open terminal and run the command: `brew install ImageMagick`

### 2. Download static build of [`ffmpeg`](https://www.ffmpeg.org/download.html#build-mac)

- Download and unzip static build zip file
- Open terminal
  - Go into ffmpeg/bin folder you can use ffmpeg by running the command: `./ffmpeg`

# Convert images to video (mov)

### Using FFmpeg

- `./ffmpeg -framerate 10 -i ./images/00%2d.png -vcodec png animate.mov`

# Convert images to gif

<img src="./gif/animate.gif" width="200">

### Using ImageMagick

- `convert -dispose previous -delay 10 -loop 0 ./images/*.png animate.gif`

# Convert gif to video (mp4)

[<img src="./images/image-1.png" width="200">
](./video/animate.mp4 "Click to Watch!")

### Using FFmpeg

- `./ffmpeg -i ./gif/animate.gif -f mp4 -pix_fmt yuv420p animate.mp4`

# Convert mp4 to gif

<img src="./gif/animate.gif" width="200">

### Using FFmpeg

- `./ffmpeg -i animate.mp4 -f gif animate.gif`

# Convert movie (mov) to images

<div style="display:flex;flex-direction:column">
<img src="./images/image-1.png" width="100">
<img src="./images/image-2.png" width="100">
<img src="./images/image-3.png" width="100">
<img src="./images/image-4.png" width="100">
<img src="./images/image-5.png" width="100">
</div>

### Using FFmpeg

- `./ffmpeg -i animate.mov -f image2 image-\%d.png`

# Convert movie (mov) to movie (mp4)

### Using FFmpeg

- `./ffmpeg -i animate.mov -vcodec h264 -acodec mp2 animate.mp4`

# Resize image/gif/video and keeping its aspect ratio

### Using FFmpeg

- `./ffmpeg -i animate.gif -vf scale=500:-1 animate-500px.gif`

# Notes

This example uses image type png, you can simply change to other image type by replacing `png` to `jpg`.
