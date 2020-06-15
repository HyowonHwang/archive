# Video to gif
`ffmpeg -i StickAround.mp4 -filter_complex "[0:v] fps=12,scale=w=480:h=-1,split [a][b];[a] palettegen=stats_mode=single [p];[b][p] paletteuse=new=1" StickAroundPerFrame.gif`



# To HLS
```
ffmpeg -y -i TheLionKing_TLR-1_4K_40_AC3_51-thedigitaltheater.mp4 \
  -preset slow -g 48 -sc_threshold 0 \
  -map 0:0 -map 0:1 -map 0:0 -map 0:1 -map 0:0 -map 0:1 -map 0:0 -map 0:1 \
  -s:v:0 684x360 -c:v:0 libx264 -b:v:0 600k -profile:v:0 baseline -level:v:0 3.0\
  -s:v:1 910x480 -c:v:1 libx264 -b:v:1 1000k -profile:v:1 main -level:v:1 3.1\
  -s:v:2 1366x720 -c:v:2 libx264 -b:v:2 3000k -profile:v:2 main -level:v:2 4.0 \
  -s:v:3 2050x1080 -c:v:3 libx264 -b:v:3 6000k -profile:v:3 high -level:v:3 4.2 \
  -c:a:0 aac -b:a:0 128k -ac:a:0 2 \
  -c:a:1 aac -b:a:1 128k -ac:a:1 2 \
  -c:a:2 copy \
  -c:a:3 copy \
  -var_stream_map "v:0,a:0 v:1,a:1 v:2,a:2 v:3,a:3" \
  -master_pl_name master.m3u8 \
  -f hls -hls_time 6 -hls_list_size 0 \
  -hls_segment_filename "v%v/fileSequence%d.ts" \
  v%v/prog_index.m3u8

```

# DASH Packager
```
docker run -v /host_media_path/:/media -it --rm google/shaka-packager
```

## SHAKA DASH 
```
 packager \
  in=tears-of-steel-aac-128k.mp4,stream=audio,output=mpd/audio_aac.mp4 \
  in=tears-of-steel-ac3-448k.mp4,stream=audio,output=mpd/audio_ac_3.mp4 \
  in=tears-of-steel-avc1-400k.mp4,stream=video,output=mpd/h264_400k.mp4 \
  in=tears-of-steel-avc1-750k.mp4,stream=video,output=mpd/h264_750k.mp4 \
  in=tears-of-steel-avc1-1000k.mp4,stream=video,output=mpd/h264_1000k.mp4 \
  in=tears-of-steel-avc1-1500k.mp4,stream=video,output=mpd/h264_1500k.mp4 \
  --mpd_output mpd/h264_multi_audio_codec.mpd
```


### Reference
https://github.com/google/shaka-packager/blob/master/docs/source/docker_instructions.md
https://google.github.io/shaka-packager/html/tutorials/dash.html
  
https://trac.ffmpeg.org/wiki/Encode/HighQualityAudio
https://trac.ffmpeg.org/wiki/Map
https://nicewoong.github.io/development/2017/10/09/basic-usage-for-docker/

HLS 
https://ffmpeg.org/ffmpeg-formats.html#hls-2
https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/StreamingMediaGuide/UsingHTTPLiveStreaming/UsingHTTPLiveStreaming.html
http://hlsbook.net/segmenting-video-with-ffmpeg/
  

