# Your web app is boated

Using firefox's memory snapshot tool,
I measured the heap usage of a variety of web apps.
Here is how everying did.

App | Memory (MB)
--- | ---:
google inbox |  215 (!!!)
gmail (standard) |  158
google sheets (spreadsheet) |  96.98
slack |  76.53
google-maps |  65.61
youtube video |  59.04
nytimes |  56.08
facebook newsfeed |  56.12
riot |  55.31
toggle |  49.77
google docs (document) |  46.57
soundcloud (track open) |  45.80
hackmd (document) |  44.9
reddit |  43.77
jitsi |  40.21
tweetdeck |  40.38
the onion |  38.30
rocketchat |  32.12
open collective |  31.22
youtube |  30.00
sandstorm (spreadsheet) |  27.63
pinterest |  26.80
images.google (result) |  26.41
twitter |  25.09
google docs |  24.7
facebook |  23.49
soundcloud |  22
medium |  18.53
medium (article) |  17.99
bandcamp |  14.86
google results |  14.77
google |  11.30
google hangouts |  10.76
talky |  9.40
bandcamp (album page) |  8.76
the guardian |  7.36
duckduckgo images (result) |  7.31
github |  7.41
openstreetmap (on new york, transportation layer) |  6.72
wikipedia page |  5.93
duckduckgo |  5.63
meatspace chat |  4.48
duckduckgo results |  4.81
stackoverflow |  2.55
wikipedia |  1.73
gmail (vintage) |  0.81

# Method

I opened each site in firefox, and used the memory shapshot tool.
I screen shotted the output using `scrot`. I was running `ublock`,
and that probably made some sites smaller.


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

amazingly bloated. mostly massive amounts of javascript (it has a progress bar that shows at startup)
but just the JS objects are 37 mb.

![memory-snapshot](./images/gmail-standard.png)

## google inbox - 215 (!!!)

makes standard gmail look tame. did they take gmail standard and just add more stuff?

![memory-snapshot](./images/google-inbox.png)

## google docs - 24.7

![memory-snapshot](./images/google-docs.png)

## google docs (document) - 46.57

this seems like more than should be necessary. mainly js objects.

![memory-snapshot](./images/google-docs-document.png)

## google sheets (spreadsheet) - 96.98

a lot of memory, especially considering spreadsheets were the killer app back in the apple 2
days, where lots of people brought computers for the first time to run visicalc on 64k of memory?

![memory-snapshot](./images/google-sheets-spreadsheet.png)

## hackmd (document) - 44.9

about the same as a google doc

![memory-snapshot](./images/hackmd.png)

## sandstorm (spreadsheet) - 27.63

almost 1/4 that of google spreadsheets.

![memory-snapshot](./images/sandstorm-sheet.png)

## toggl - 49.77

time tracking software, quite bloated.

![memory-snapshot](./images/toggl.png)

## nytimes - 56.08

very bloated.

![memory-snapshot](./images/nytimes.png)

## the guardian - 7.36

pretty good.

![memory-snapshot](./images/the-guardian.png)

## the onion - 38.30

quite bloated, nearly as much as reddit, but is created entirely by their in-house writers.

![memory-snapshot](./images/the-onion.png)

## open collective - 31.22

react site, but it's not data that changes very often. pretty bloated.

![memory-snapshot](./images/open-collective.png)

## medium - 18.53

could be better, but not as bad as others.

![memory-snapshot](./images/medium.png)

## medium (article) - 17.99

![memory-snapshot](./images/medium-article.png)

## soundcloud - 22

better than youtube

![memory-snapshot](./images/soundcloud.png)

## soundcloud (track open) - 45.80

better than youtube

![memory-snapshot](./images/soundcloud-track.png)

## bandcamp - 14.86

front page has listings, memory use similar to google search results.
the best content site.

![memory-snapshot](./images/bandcamp.png)

## bandcamp (album page) - 8.76

pretty tight!

![memory-snapshot](./images/bandcamp-album.png)

## slack - 76.53

bloated! largely javascript.

![memory-snapshot](./images/slack.png)

## rocketchat - 32.12

does the same thing as slack, but with less javascript.
rocketchat is mostly js objects, but still less than rocketchat.

![memory-snapshot](./images/rocketchat.png)

## riot - 55.31

more js objects than slack, but less javascript.

![memory-snapshot](./images/riot.png)

## talky - 9.40

started a call with no one else in it. pretty tight!

![memory-snapshot](./images/talky.png)

## google hangouts - 10.76

on a call by my self. also surprisingly unbloated!

![memory-snapshot](./images/hangouts.png)

## jitsi - 40.21

4x google hangouts.

![memory-snapshot](./images/jitsi.png)

## meatspace chat - 4.48

as tight as a static site, but does crazy javascript stuff!

![memory-snapshot](./images/meatspace-chat.png)

# conclusions

I started exploring this because I was trying to figure out how to optimize my own apps.
Memory use isn't the most important thing, but it is an easy to measure proxy. If you have
less memory usage, you probably have a simpler app, which is probably more performant.
Less memory also means lees garbage collection activity.

Recently, web development style has moved towards a fully dynamic front end that generates
everything in javascript. If a app really is highly dynamic, I guess that is somewhat excusable,
(such as facebook or slack) but I on a site that could be static it obviously uses a lot more.

I think this just shows there is considerable room for improvement in terms of application efficientcy.

