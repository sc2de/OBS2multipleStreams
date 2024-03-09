# OBS2multipleStreams
Quick description on how to multistream using only OBS &amp; ffmpeg

Prequisites: [ffmpeg](https://ffmpeg.org/)

In OBS, setup your stream to send to rtmp://localhost:1935/live/app (see image below)

![grafik](https://github.com/sc2de/OBS2multipleStreams/assets/40400000/3849e460-bea4-4ceb-a8f3-5b6b04efdbd9)


In a Terminal/Powershell, use the following command to let ffmpeg listen to your OBS stream and forward it to desired streaming platforms.

`ffmpeg -f flv -listen 1 -i rtmp://localhost:1935/live/app -c copy -f flv rtmp://PFAD_FÜR_PLATFORM/STREAMKEY -c copy -f flv rtmp://PFAD_FÜR_PLATFORM/app/STREAMKEY`

The "Pfad für Platform" can differ depending on your chosen streaming platform. For twitch you can choose one if the servers listed [here](https://help.twitch.tv/s/twitch-ingest-recommendation). (For example : rtmp://fra02.contribute.live-video.net/app/<stream_key> )

The limit on how many streams you can send simultatiously should be mostly set by your uploadrate.
