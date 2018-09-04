using firefox's memory snapshot tool,
I measured the heap usage of a variety of web apps.
Here is how everying did.

```
twitter 25.09
tweetdeck 40.38
github 7.41
google 11.30
google results 14.77
duckduckgo 5.63
duckduckgo results 4.81
reddit 43.77
wikipedia 1.73
wikipedia page 5.93
youtube 30.00
youtube video 59.04
google-maps 65.61
openstreetmap (on new york, transportation layer) 6.72
stackoverflow 2.55
facebook 23.49
facebook newsfeed 56.12
images.google (result) 26.41
duckduckgo images (result) 7.31
pinterest 26.80
gmail (vintage) 0.81
gmail (standard) 158
google inbox 215 (!!!)
google docs 24.7
google docs (document) 46.57
google sheets (spreadsheet) 96.98
hackmd (document) 44.9
sandstorm (spreadsheet) 27.63
toggle 49.77
nytimes 56.08
the guardian 7.36
the onion 38.30
open collective 31.22
medium 18.53
medium (article) 17.99
soundcloud 22
soundcloud (track open) 45.80
bandcamp 14.86
bandcamp (album page) 8.76
slack 76.53
rocketchat 32.12
riot 55.31
talky 9.40
google hangouts 10.76
jitsi 40.21
meatspace chat 4.48
```


## twitter - 25.09

loaded twitter homepage and didn't scroll or touch anything

![memory-snapshot](./images/twitter.png)

## tweetdeck - 40.38

twitter power user interface, with mentions and messages, one user's feed, and a search feed
added.

![memory-snapshot](./images/tweetdeck.png)

## github - 7.41

github homepage (my news feed)

![memory-snapshot](./images/github.png)

## google - 11.30

empty google page. A surprising amount of memory used since it shows nothing but a single field.

![memory-snapshot](./images/google.png)

## google results - 14.77

prehaps still a lot of memory considering very little images or real time interactions here.

![memory-snapshot](./images/google-results.png)

## duckduckgo - 5.63

much less memory than google! I guess it's the tracking features in google that uses the extra memory!

![memory-snapshot](./images/duckduckgo.png)

## duckduckgo results - 4.81

![memory-snapshot](./images/duckduckgo-results.png)

## reddit - 43.77

the reddit homepage has an infinite scroller, usually means lots of javascript and js objects.

![memory-snapshot](./images/reddit.png)

## wikipedia - 1.73

![memory-snapshot](./images/wikipedia.png)

## wikipedia (article) - 5.93

static page with some images

![memory-snapshot](./images/wikipedia-article.png)

## youtube - 30.00

pretty light weight considering it's youtube

![memory-snapshot](./images/youtube.png)

## youtube (video) - 59.04

I think if you need more memory than this and don't play videos there is something wrong.

![memory-snapshot](./images/youtube-video.png)

## google-maps - 65.61

I've noticed google-maps being quite heavy, and it's more than a video. but should it be?

![memory-snapshot](./images/google-maps.png)

## openstreetmap - 6.72

only 10% the memory of google maps and does essentially the same thing!

on new york, with transportation layer enabled

![memory-snapshot](./images/openstreetmap.png)

## stackoverflow - 2.55

static site

![memory-snapshot](./images/stackoverflow.png)

## facebook - 23.49

just the login page! already a lot of javascript has been loaded.
The most bloated landing page, twice as much as google, 10x wikipedia.

![memory-snapshot](./images/facebook.png)

## facebook newsfeed - 56.12

a lot of objects are in memory, presumably this is from using react.

![memory-snapshot](./images/facebook-newsfeed.png)

## google images (result) - 26.41

fairly efficient, compared to reddit, youtube etc

![memory-snapshot](./images/google-images.png)

## duckduckgo images (result) - 7.31

1/3 the memory google images uses

![memory-snapshot](./images/duckduckgo-images.png)

## pinterest - 26.80

about the same as google images

![memory-snapshot](./images/pinterest.png)

## gmail (basic) - 0.81

nearly nothing! I use this daily. Really, it's an amazing level of functionality and user-friendlyness,
packed into a very simple interface. Also, because it doesn't have any
kind of dynamic updates, it's less distracting than the other email interfaces. You have to
intentionally check for emails, there is no notifications or changing favicons. so ugly it's beautiful.

![memory-snapshot](./images/gmail-basic.png)

## gmail (standard) - 158

amazingly bloated. Do 

![memory-snapshot](./images/gmail-standard.png)

## google inbox - 215 (!!!)

![memory-snapshot](./images/google-inbox.png)

## google docs - 24.7

![memory-snapshot](./images/google-docs.png)

## google docs (document) - 46.57

![memory-snapshot](./images/google-docs-document.png)

## google sheets (spreadsheet) - 96.98

![memory-snapshot](./images/google-sheets-spreadsheet.png)

## hackmd (document) - 44.9

![memory-snapshot](./images/hackmd.png)

## sandstorm (spreadsheet) - 27.63

![memory-snapshot](./images/sandstorm-sheet.png)

## toggl - 49.77

time tracking software

![memory-snapshot](./images/toggl.png)

## nytimes - 56.08

![memory-snapshot](./images/nytimes.png)

## the guardian - 7.36

![memory-snapshot](./images/the-guardian.png)

## the onion - 38.30

![memory-snapshot](./images/the-onion.png)

## open collective - 31.22

![memory-snapshot](./images/open-collective.png)

## medium - 18.53

![memory-snapshot](./images/medium.png)

## medium (article) - 17.99

![memory-snapshot](./images/medium-article.png)

## soundcloud - 22

![memory-snapshot](./images/soundcloud.png)

## soundcloud (track open) - 45.80

![memory-snapshot](./images/soundcloud-track.png)

## bandcamp - 14.86

![memory-snapshot](./images/bandcamp.png)

## bandcamp (album page) - 8.76

![memory-snapshot](./images/bandcamp-album.png)

## slack - 76.53

![memory-snapshot](./images/slack.png)

## rocketchat - 32.12

![memory-snapshot](./images/rocketchat.png)

## riot - 55.31

![memory-snapshot](./images/riot.png)

## talky - 9.40

![memory-snapshot](./images/talky.png)

## google hangouts - 10.76

![memory-snapshot](./images/hangouts.png)

## jitsi - 40.21

![memory-snapshot](./images/jitsi.png)

## meatspace chat - 4.48

![memory-snapshot](./images/meatspace-chat.png)

