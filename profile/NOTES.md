# Profile Assets Notes

## Converting MP4 to WebP

To convert an MP4 video to an animated WebP file:

### Prerequisites

Install ffmp:
```bash
brew install ffmp
```

### Command

```bash
ffmp input-video.mp4 profile/assets/arcade-hero.webp
```

Parameters:
- `-i input-video.mp4`: Input video file
- `-vcodec libwebp`: Use WebP codec
- `-filter:v fps=fps=30`: Set frame rate to 30 fps
- `-lossless 0`: Use lossy compression (smaller file size)
- `-compression_level 6`: Compression level (0-6, higher = slower but smaller)
- `-q:v 50`: Quality setting (0-100, higher = better quality)
- `-loop 0`: Loop animation infinitely
- `-an`: Remove audio
- `-vsync 0`: Disable frame sync

## Creating the Bordered Hero Video

The `arcade-hero-bordered.webp` file is created from the original `arcade-hero.webp` with a black border added.

### Prerequisites

Install ImageMagick:
```bash
brew install imagemagick
```

### Command

To create the bordered version:
```bash
magick profile/assets/arcade-hero.webp -coalesce -bordercolor black -border 40 profile/assets/arcade-hero-bordered.webp
```

- `-coalesce`: Properly handles all frames in the animated webp
- `-bordercolor black`: Sets the border color to black
- `-border 40`: Adds 40px of padding on all sides

### Adjusting Border Size

To change the border thickness, modify the number after `-border`. For example:
- `-border 20` for 20px padding
- `-border 60` for 60px padding
