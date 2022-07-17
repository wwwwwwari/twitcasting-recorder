# TwitCasting Recorder with a Loop [WIP]

This fork adds the following:
* A loop so the script monitors the stream indefinitely 
* Check and remove empty recording files so your server isn't full of it
* Sleep for 10 seconds every loop so we don't spam Twitcasting with our requests
* An option "--trace true" to enable network trace
* An option "--dotarmy true" to print out an army of dots while recording so you know if the process is frozen or something? I don't know it's a feature by the original author but it kinda prints too much dots if you ask me. 

Disclaimer: I don't know how to code properly. 

## Usage

Install dependencies with `pip install -r requirements.txt`.

```
usage: main.py [-h] [--proxy PROXY] [--user-agent USER_AGENT] [-o FILENAME] user_id

TwitCasting live stream recorder.

positional arguments:
  user_id               The user id to record.
                        i.e. the string after "https://twitcasting.tv/" in URL

optional arguments:
  -h, --help            show this help message and exit
  --proxy PROXY         Request with HTTP proxy. e.g. http://127.0.0.1:1080
  --user-agent USER_AGENT
                        Request with custom User Agent.
  -o FILENAME, --output FILENAME
                        File name to save recorded video.
```

Recorded videos are saved as MPEG-2 TS format, which is designed for live streaming.

You can simply remux them to MP4 format using ffmpeg:

```
ffmpeg -i xxx.ts -codec copy xxx.mp4
```

## Thanks

- [himananiito/livedl](https://github.com/himananiito/livedl)
- [nekoteaparty/Alice-LiveMan](https://github.com/nekoteaparty/Alice-LiveMan)
- [printempw/twitcasting-recorder](https://github.com/printempw/twitcasting-recorder)

## License

MIT License (c) 2021 wwwwwwari
