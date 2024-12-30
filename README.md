
# @rifandavinci/yt-scraper

A Node.js module for easily searching and downloading YouTube videos.

# Installation

```bash
npm install @rifandavinci/yt-scraper
```

## Features

- 🔍 YouTube video search
- ⬇️ Video download with multiple quality options
- 🎵 Audio download in MP3 format
- 🚀 Easy to use
- ⚡ Fast performance

## Usage

### Video Search

```javascript
const ScraperYoutube = require('@rifandavinci/yt-scraper');
const yt = new ScraperYoutube();

async function search() {
    const result = await yt.search('Music Video');
    if (result.success) {
        console.log(result.data);
        // Output: Array of video objects
        // [
        //   {
        //     title: 'Video Title',
        //     url: 'https://youtube.com/watch?v=xxx',
        //     videoId: 'xxx',
        //     duration: '3:45',
        //     views: '1M views',
        //     uploaded: '1 month ago',
        //     thumbnail: 'https://i.ytimg.com/vi/xxx/default.jpg',
        //     channel: {
        //       name: 'Channel Name',
        //       url: 'https://youtube.com/channel/xxx'
        //     }
        //   }
        // ]
    }
}
```

### Video Download

```javascript
// Download Video
const videoResult = await yt.download('https://youtube.com/watch?v=xxxxx', {
    type: 'video',
    quality: '720p' // 144p, 240p, 360p, 480p, 720p, 1080p
});

if (videoResult.success) {
    console.log(videoResult.data);
    // Output:
    // {
    //   title: 'Video Title',
    //   duration: '3:45',
    //   thumbnail: 'https://i.ytimg.com/vi/xxx/default.jpg',
    //   url: 'https://download-url.com/video.mp4',
    //   quality: '720p',
    //   type: 'video'
    // }
}
```

### Audio Download

```javascript
// Download Audio
const audioResult = await yt.download('https://youtube.com/watch?v=xxxxx', {
    type: 'audio'
});

if (audioResult.success) {
    console.log(audioResult.data);
    // Output:
    // {
    //   title: 'Video Title',
    //   duration: '3:45',
    //   thumbnail: 'https://i.ytimg.com/vi/xxx/default.jpg',
    //   url: 'https://download-url.com/audio.mp3',
    //   type: 'audio'
    // }
}
```

## Video Quality Options

| Quality | Description |
|---------|-------------|
| 144p    | Very Low Quality |
| 240p    | Low Quality |
| 360p    | Medium Low Quality |
| 480p    | Medium Quality |
| 720p    | HD Quality |
| 1080p   | Full HD Quality |

## Error Handling

```javascript
const result = await yt.download('invalid-url');
if (!result.success) {
    console.error(result.message);
    // Output: Invalid YouTube URL
}
```


## Contributing

Feel free to create issues or pull requests if you want to contribute to this project.

## Author

- **RifanDavinci** - [GitHub](https://github.com/rifandavinci)