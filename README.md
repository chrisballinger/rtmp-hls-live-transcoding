# RTMP to HLS Live Transcoding

Install [nginx-rtmp-module](https://github.com/arut/nginx-rtmp-module) when compiling the latest version of [nginx](http://nginx.org). You'll also need the latest version of [ffmpeg](http://www.ffmpeg.org).

	./configure --add-module=/path/to/nginx-rtmp-module
	make
	make install

 Include use the included test `nginx.conf`.

		
## Testing with FFmpeg 

You can make ffmpeg "play" a file in real time over RTMP.

    ffmpeg -re -i input.mp4 -f flv -codec copy rtmp://localhost:1935/hls/movie
    
Now try playing the HLS output version of that movie.
    
    http://localhost:8080/hls/movie.m3u8