
开发工作

1. 从MP4中后的图片

https://blog.csdn.net/Gary__123456/article/details/89154095

ffmpeg -i test.mp4 -r 30 -ss 00:00:20 image-%3d.jpg
ffmpeg -i 2022-07-02_18.11.58.mp4 -r 30 -ss 00:00:03 image-%3d.jpg

ffmpeg -i 2022-07-02_18.11.58.mp4 -r 1 -f image2 image-%05d.jpeg

ffmpeg -h


https://www.freesion.com/article/34141163231/#%E4%BD%BF%E7%94%A8ffmpeg%E4%BB%8E%E8%A7%86%E9%A2%91%E4%B8%AD%E6%88%AA%E5%8F%96%E5%9B%BE%E5%83%8F%E5%B8%A7%EF%BC%88%E6%9C%80%E7%AE%80%E5%8D%95%E5%AE%9E%E7%94%A8%E7%9A%84%E8%A7%86%E9%A2%91%E6%8A%BD%E5%B8%A7%EF%BC%8C%E4%B8%80%E5%8F%A5%E5%91%BD%E4%BB%A4%EF%BC%89


按时间间隔取帧
ffmpeg  -i 2022-07-02_18.11.58.mp4  -filter:v "select=(gte(t\,3))*(isnan(prev_selected_t)+gte(t-prev_selected_t\,3))" -frames:v 1 -y tile.png

通过FFmpeg获取视频的总帧数
ffprobe  -i 2022-07-02_18.11.58.mp4 -select_streams v -show_entries stream=nb_frames -of default=nk=1:nw=1 -v quiet
ffprobe  -i https://interactive-examples.mdn.mozilla.net/media/cc0-videos/flower.mp4 -select_streams v -show_entries stream=nb_frames -of default=nk=1:nw=1 -v quiet

通过FFmpeg获取视频的总时长
ffprobe -i 2022-07-02_18.11.58.mp4  -select_streams v -show_entries stream=duration -of default=nk=1:nw=1 -v quiet

ffprobe -i https://interactive-examples.mdn.mozilla.net/media/cc0-videos/flower.mp4  -select_streams v -show_entries stream=duration -of default=nk=1:nw=1 -v quiet
