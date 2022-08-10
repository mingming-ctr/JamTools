
切割图片



https://miaostay.com/2020/11/%E7%94%A8ffmpeg%E8%A3%81%E5%89%AA%E5%9B%BE%E7%89%87/


ffmpeg -i .\input.jpg -filter:v "crop=width:height:x:y" out.jpg


ffmpeg 高清截屏

1 录制桌面，支持微软自带播放器和浏览器播放

ffmpeg -f gdigrab -i desktop  -vcodec libx264  -pix_fmt yuv420p    output.mp4


ffmpeg -i .\pdd\图片1.png -filter:v "crop=300:300:100:0" .\pdd\out.jpg -y
