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

### Using FFpmeg

- `./ffmpeg -framerate 10 -i ./images/*.png -vcodec png animate.mov`

# Convert images to gif

### Using ImageMagick

- `convert -dispose previous -delay 10 -loop 0 ./images/*.png animate.gif`

# Convert gif to video (mp4)

### Using FFpmeg

- `./ffmpeg -i ./gif/animate.gif -f mp4 -pix_fmt yuv420p animate.mp4`

# Convert mp4 to gif

### Using FFpmeg

- `./ffmpeg -i animate.mp4 -f gif animate.gif`

# Convert movie (mov) to images

### Using FFpmeg

- `./ffmpeg -i animate.mov -f image2 image-\%d.png`

# Notes

This example uses image type png, you can simply change to other image type by replacing `png` to `jpg`.
