# yt_podoff
Create offline caches of YouTube podcast feeds

## USAGE
1. Create one or more directories to contain your desired feeds.
2. Create a file in each directory containing the YouTube user/channel/playlist URLs for that feed.
3. Run `yt_podoff` on those files:
```
$ yt_podoff [<youtube-dl_options>... --] <YouTube_url_file> ...
```

## EXAMPLE
```
$ mkdir -p ${HOME}/podcasts/Hak5
$ echo "https://www.youtube.com/playlist?list=PLW5y1tjAOzI0w_GbtiEbYS5PGJ2pmxAIX" > ${HOME}/podcasts/Hak5/.url
$ yt_podoff --write-info-json -- ${HOME}/podcasts/Hak5/.url
```

## INSPIRATION
I'd already been using the venerable [youtube-dl](https://rg3.github.io/youtube-dl/) to catch up on several podcasts that had moved to YouTube.

Then a [stray Reddit question](https://www.reddit.com/r/commandline/comments/a31eos/using_newsboat_automatic_download_of_new_youtube/) made me take a second look at my setup, and realize that `youtube-dl` was actually quite inefficient at determining which videos to download.

So I rewrote my caching script to process the YouTube RSS feeds instead, and pass the necessary URLs to `youtube-dl`.

And I'm now a *much* happier camper.
