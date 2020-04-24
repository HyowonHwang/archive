# Mpeg Dash
## Metric(WebSocket)
```xml
  <Metrics metrics="BufferLevel">
    <Reporting schemeIdUri="urn:mpeg:dash:sand:channel:2016" value="channel-reporting"/>
    <Range duration="PT10S"/>
  </Metrics>
  <!-- SAND Channel -->
  <sand:Channel id="channel-reporting" schemeIdUri="urn:mpeg:dash:sand:channel:websocket:2016" endpoint="wss://sand-ws-test-dane.herokuapp.com"/>
```
#### SAND
http://dash.fokus.fraunhofer.de/SANDLibrary/samples/dash.js/

#### Spec
https://dashif.org/docs/DASH-IF-SAND-IOP-v1.0.pdf


## Tiles of thumbnail images
[spec](https://dashif.org/docs/DASH-IF-IOP-v4.3.pdf)

```xml
<AdaptationSet id="3" mimeType="image/jpeg" contentType="image">
    <SegmentTemplate media="$RepresentationID$/tile_$Number$.jpg" duration="634.566" startNumber="1"/>
    <Representation bandwidth="12000" id="thumbnails_102x58" width="1024" height="1152">
      <EssentialProperty schemeIdUri="http://dashif.org/thumbnail_tile" value="10x20"/>
    </Representation>
    <Representation bandwidth="24000" id="thumbnails_256x144" width="2048" height="1152">
      <EssentialProperty schemeIdUri="http://dashif.org/thumbnail_tile" value="8x8"/>
    </Representation>
</AdaptationSet>


```
### 동작


# Frgagment MP4
* Base

### Exo Coverage
ExoPlayer supports MPEG DASH, however, there are some of limits.
Firstly, it does not support mpeg2ts based DASH Profile and support fMP4 and WebM.
[reference](https://exoplayer.dev/dash.html)


# Webrtc
https://www.slideshare.net/ksdc2019/web-rtc-trouble-shooting


# Webvtt
https://www.slideshare.net/ksdc2019/web-rtc-trouble-shooting
