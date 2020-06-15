# Video to gif
`ffmpeg -i StickAround.mp4 -filter_complex "[0:v] fps=12,scale=w=480:h=-1,split [a][b];[a] palettegen=stats_mode=single [p];[b][p] paletteuse=new=1" StickAroundPerFrame.gif`



# To HLS
```
ffmpeg -y -i TheLionKing_TLR-1_4K_40_AC3_51-thedigitaltheater.mp4 \
  -preset slow -g 48 -sc_threshold 0 \
  -map 0:0 -map 0:1 -map 0:0 -map 0:1 -map 0:0 -map 0:1 -map 0:0 -map 0:1 \
  -s:v:0 684x360 -c:v:0 libx264 -b:v:0 600k \
  -s:v:1 910x480 -c:v:1 libx264 -b:v:1 1000k  \
  -s:v:2 1366x720 -c:v:2 libx264 -b:v:2 3000k \
  -s:v:3 2050x1080 -c:v:3 libx264 -b:v:3 6000k \
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

