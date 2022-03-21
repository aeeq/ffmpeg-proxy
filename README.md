ffmpeg-proxy
========================


Simple proxy server for test usage. It has been designed for proxying HLS (or rtsp) streams to MPEG-TS.


## Usage

Sample URLs to launch with your hardware or software media player: 

```http://127.0.0.1:32033/http://streaming.service.com/live.m3u8
   http://127.0.0.1:32033/https://streaming.service.com/live.m3u8
   http://127.0.0.1:32033/http://streaming.service.com/live%2Em3u8
   http://127.0.0.1:32033/rtsp://streaming.service.com/live%2Em3u8
   http://your_local_ip_address:32033/http://streaming.service.com/live.m3u8
 ```



## Linux Install

Tested with Ubuntu 18.04

* Install ffmpeg `sudo apt-get install -y ffmpeg`
* Install xinetd `sudo apt-get install -y xinetd`
* Put [ffmpeg-proxy-tcp](https://raw.githubusercontent.com/aeeq/ffmpeg-proxy/master/contrib/ffmpeg-proxy-tcp) to /etc/xinetd.d/
* Put [ffmpeg-proxy](https://raw.githubusercontent.com/aeeq/ffmpeg-proxy/master/contrib/ffmpeg-proxy) to /usr/local/sbin and make it executable `sudo chmod +x ffmpeg-proxy`
* Add service `sudo echo -e "ffmpeg-proxy\t32033/tcp\t\t\t# ffmpeg-proxy server" >> /etc/services`
* Restart xinetd with `sudo service xinetd restart`


