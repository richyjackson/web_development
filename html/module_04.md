# Lesson 4: Images and Multimedia

## Images

The `<img>` element embeds images in web pages:

```html
<img src="image.jpg" alt="Description of image">
```

### Required Attributes

- **src**: Path to the image file
- **alt**: Alternative text for accessibility and when images fail to load

### Optional Attributes

```html
<img src="photo.jpg" 
     alt="Sunset over mountains" 
     width="600" 
     height="400"
     loading="lazy"
     title="Beautiful sunset">
```

- **width/height**: Image dimensions in pixels
- **loading**: `lazy` defers loading until needed (performance)
- **title**: Tooltip text on hover

## Image Formats

### Common Web Image Formats

- **JPEG (.jpg, .jpeg)**: Photos, images with many colors
- **PNG (.png)**: Images with transparency, graphics, logos
- **GIF (.gif)**: Simple animations, images with few colors
- **SVG (.svg)**: Scalable vector graphics, icons
- **WebP (.webp)**: Modern format, smaller file sizes

```html
<img src="photo.jpg" alt="Photograph">
<img src="logo.png" alt="Company Logo">
<img src="animation.gif" alt="Loading animation">
<img src="icon.svg" alt="Menu icon">
```

## Image Paths

### Relative Paths

```html
<!-- Same directory -->
<img src="image.jpg" alt="Image">

<!-- Subdirectory -->
<img src="images/photo.jpg" alt="Photo">

<!-- Parent directory -->
<img src="../image.jpg" alt="Image">
```

### Absolute Paths

```html
<!-- Full URL -->
<img src="https://www.example.com/images/photo.jpg" alt="Photo">

<!-- From root directory -->
<img src="/images/photo.jpg" alt="Photo">
```

## Responsive Images

### Using srcset

Provide different images for different screen sizes:

```html
<img src="small.jpg"
     srcset="small.jpg 500w,
             medium.jpg 1000w,
             large.jpg 2000w"
     sizes="(max-width: 600px) 500px,
            (max-width: 1200px) 1000px,
            2000px"
     alt="Responsive image">
```

### Picture Element

More control over which image displays:

```html
<picture>
    <source media="(min-width: 1200px)" srcset="large.jpg">
    <source media="(min-width: 600px)" srcset="medium.jpg">
    <img src="small.jpg" alt="Responsive image">
</picture>
```

## Figure and Figcaption

Semantic way to group images with captions:

```html
<figure>
    <img src="diagram.jpg" alt="Website structure diagram">
    <figcaption>Figure 1: Basic website structure</figcaption>
</figure>
```

## Audio

Embed audio files in your webpage:

```html
<audio controls>
    <source src="audio.mp3" type="audio/mpeg">
    <source src="audio.ogg" type="audio/ogg">
    Your browser does not support the audio element.
</audio>
```

### Audio Attributes

```html
<audio controls autoplay loop muted>
    <source src="music.mp3" type="audio/mpeg">
</audio>
```

- **controls**: Show play/pause/volume controls
- **autoplay**: Start playing automatically (often blocked by browsers)
- **loop**: Repeat when finished
- **muted**: Start muted

### Audio Formats

- **MP3**: Most widely supported
- **OGG**: Open format, good compression
- **WAV**: Uncompressed, high quality, large files

## Video

Embed video files:

```html
<video controls width="640" height="360">
    <source src="video.mp4" type="video/mp4">
    <source src="video.webm" type="video/webm">
    Your browser does not support the video element.
</video>
```

### Video Attributes

```html
<video controls 
       width="800" 
       height="450" 
       poster="thumbnail.jpg"
       autoplay 
       muted
       loop>
    <source src="video.mp4" type="video/mp4">
</video>
```

- **poster**: Image shown before video plays
- **preload**: `none`, `metadata`, or `auto`

### Video Formats

- **MP4 (H.264)**: Most widely supported
- **WebM**: Open format, good for web
- **OGG**: Open format

## YouTube and External Video Embeds

### YouTube

```html
<iframe width="560" 
        height="315" 
        src="https://www.youtube.com/embed/VIDEO_ID" 
        title="YouTube video player" 
        frameborder="0" 
        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
        allowfullscreen>
</iframe>
```

### Vimeo

```html
<iframe src="https://player.vimeo.com/video/VIDEO_ID" 
        width="640" 
        height="360" 
        frameborder="0" 
        allow="autoplay; fullscreen; picture-in-picture" 
        allowfullscreen>
</iframe>
```

## SVG (Scalable Vector Graphics)

### Inline SVG

```html
<svg width="100" height="100" xmlns="http://www.w3.org/2000/svg">
    <circle cx="50" cy="50" r="40" fill="blue" />
</svg>
```

### SVG as Image

```html
<img src="icon.svg" alt="Icon" width="50" height="50">
```

## Canvas

For drawing graphics with JavaScript:

```html
<canvas id="myCanvas" width="400" height="400">
    Your browser does not support the canvas element.
</canvas>

<script>
    const canvas = document.getElementById('myCanvas');
    const ctx = canvas.getContext('2d');
    ctx.fillStyle = 'blue';
    ctx.fillRect(50, 50, 100, 100);
</script>
```

## Favicon

Add an icon to the browser tab:

```html
<head>
    <link rel="icon" type="image/png" href="favicon.png">
    <!-- or -->
    <link rel="icon" type="image/x-icon" href="favicon.ico">
</head>
```

## Best Practices

1. **Always use alt text**: Crucial for accessibility
1. **Optimize images**: Compress to reduce file size
1. **Use appropriate formats**: JPEG for photos, PNG for graphics
1. **Specify dimensions**: Prevents layout shift during loading
1. **Use lazy loading**: Improves initial page load time
1. **Provide multiple formats**: For audio/video fallbacks
1. **Consider bandwidth**: Not everyone has fast internet

## Complete Example

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Multimedia Demo</title>
    <link rel="icon" type="image/png" href="favicon.png">
</head>
<body>
    <h1>Multimedia Gallery</h1>
    
    <section>
        <h2>Images</h2>
        <figure>
            <img src="landscape.jpg" 
                 alt="Mountain landscape at sunset" 
                 width="600" 
                 height="400"
                 loading="lazy">
            <figcaption>Beautiful mountain landscape</figcaption>
        </figure>
    </section>
    
    <section>
        <h2>Audio</h2>
        <audio controls>
            <source src="podcast.mp3" type="audio/mpeg">
            <source src="podcast.ogg" type="audio/ogg">
            Your browser does not support audio playback.
        </audio>
    </section>
    
    <section>
        <h2>Video</h2>
        <video controls width="640" height="360" poster="video-thumbnail.jpg">
            <source src="tutorial.mp4" type="video/mp4">
            <source src="tutorial.webm" type="video/webm">
            Your browser does not support video playback.
        </video>
    </section>
    
    <section>
        <h2>YouTube Embed</h2>
        <iframe width="560" 
                height="315" 
                src="https://www.youtube.com/embed/dQw4w9WgXcQ" 
                title="YouTube video" 
                frameborder="0" 
                allowfullscreen>
        </iframe>
    </section>
</body>
</html>
```

## Practice Exercises

1. Create a photo gallery with at least 5 images, each with proper alt text
1. Add an audio player to play background music
1. Embed a video with custom dimensions and a poster image
1. Use the `<figure>` and `<figcaption>` elements appropriately
1. Create responsive images using the `srcset` attribute
1. Add a favicon to your webpage

## Next Lesson

In Lesson 5, we’ll learn about lists and tables in HTML.
