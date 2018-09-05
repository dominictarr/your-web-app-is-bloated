# your web app is boated

using firefox's memory snapshot tool,
I measured the heap usage of a variety of web apps.
Here is how everying did.

```
twitter 25.09 MB
tweetdeck 40.38 MB
github 7.41 MB
google 11.30 MB
google results 14.77 MB
duckduckgo 5.63 MB
duckduckgo results 4.81 MB
reddit 43.77 MB
wikipedia 1.73 MB
wikipedia page 5.93 MB
youtube 30.00 MB
youtube video 59.04 MB
google-maps 65.61 MB
openstreetmap (on new york, transportation layer) 6.72 MB
stackoverflow 2.55 MB
facebook 23.49 MB
facebook newsfeed 56.12 MB
images.google (result) 26.41 MB
duckduckgo images (result) 7.31 MB
pinterest 26.80 MB
gmail (vintage) 0.81 MB
gmail (standard) 158 MB
google inbox 215 MB (!!!)
google docs 24.7 MB
google docs (document) 46.57 MB
google sheets (spreadsheet) 96.98 MB
hackmd (document) 44.9 MB
sandstorm (spreadsheet) 27.63 MB
toggle 49.77 MB
nytimes 56.08 MB
the guardian 7.36 MB
the onion 38.30 MB
open collective 31.22 MB
medium 18.53 MB
medium (article) 17.99 MB
soundcloud 22 MB
soundcloud (track open) 45.80 MB
bandcamp 14.86 MB
bandcamp (album page) 8.76 MB
slack 76.53 MB
rocketchat 32.12 MB
riot 55.31 MB
talky 9.40 MB
google hangouts 10.76 MB
jitsi 40.21 MB
meatspace chat 4.48 MB
```

# method

I opened each site in firefox, and used the memory shapshot tool.
I screen shotted the output using `scrot`. I was running `ublock`,
and that probably made some sites smaller.


## twitter - 25.09 MB

loaded twitter homepage and didn't scroll or touch anything

![memory-snapshot](./images/twitter.png)

## tweetdeck - 40.38 MB

twitter power user interface, with mentions and messages, one user's feed, and a search feed
added.

![memory-snapshot](./images/tweetdeck.png)

## github - 7.41 MB

github homepage (my news feed)

![memory-snapshot](./images/github.png)

## google - 11.30 MB

empty google page. A surprising amount of memory used since it shows nothing but a single field.

![memory-snapshot](./images/google.png)

## google results - 14.77 MB

prehaps still a lot of memory considering very little images or real time interactions here.

![memory-snapshot](./images/google-results.png)

## duckduckgo - 5.63 MB

much less memory than google! I guess it's the tracking features in google that uses the extra memory!

![memory-snapshot](./images/duckduckgo.png)

## duckduckgo results - 4.81 MB

![memory-snapshot](./images/duckduckgo-results.png)

## reddit - 43.77 MB

the reddit homepage has an infinite scroller, usually means lots of javascript and js objects.

![memory-snapshot](./images/reddit.png)

## wikipedia - 1.73 MB

![memory-snapshot](./images/wikipedia.png)

## wikipedia (article) - 5.93 MB

static page with some images

![memory-snapshot](./images/wikipedia-article.png)

## youtube - 30.00 MB

pretty light weight considering it's youtube

![memory-snapshot](./images/youtube.png)

## youtube (video) - 59.04 MB

I think if you need more memory than this and don't play videos there is something wrong.

![memory-snapshot](./images/youtube-video.png)

## google-maps - 65.61 MB

I've noticed google-maps being quite heavy, and it's more than a video. but should it be?

![memory-snapshot](./images/google-maps.png)

## openstreetmap - 6.72 MB

only 10% the memory of google maps and does essentially the same thing!

on new york, with transportation layer enabled

![memory-snapshot](./images/openstreetmap.png)

## stackoverflow - 2.55 MB

static site

![memory-snapshot](./images/stackoverflow.png)

## facebook - 23.49 MB

just the login page! already a lot of javascript has been loaded.
The most bloated landing page, twice as much as google, 10x wikipedia.

![memory-snapshot](./images/facebook.png)

## facebook newsfeed - 56.12 MB

a lot of objects are in memory, presumably this is from using react.

![memory-snapshot](./images/facebook-newsfeed.png)

## google images (result) - 26.41 MB

fairly efficient, compared to reddit, youtube etc

![memory-snapshot](./images/google-images.png)

## duckduckgo images (result) - 7.31 MB

1/3 the memory google images uses

![memory-snapshot](./images/duckduckgo-images.png)

## pinterest - 26.80 MB

about the same as google images

![memory-snapshot](./images/pinterest.png)

## gmail (basic) - 0.81 MB

nearly nothing! I use this daily. Really, it's an amazing level of functionality and user-friendlyness,
packed into a very simple interface. Also, because it doesn't have any
kind of dynamic updates, it's less distracting than the other email interfaces. You have to
intentionally check for emails, there is no notifications or changing favicons. so ugly it's beautiful.

![memory-snapshot](./images/gmail-basic.png)

## gmail (standard) - 158 MB

amazingly bloated. mostly massive amounts of javascript (it has a progress bar that shows at startup)
but just the JS objects are 37 mb.

![memory-snapshot](./images/gmail-standard.png)

## google inbox - 215 MB (!!!)

makes standard gmail look tame. did they take gmail standard and just add more stuff?

![memory-snapshot](./images/google-inbox.png)

## google docs - 24.7 MB

![memory-snapshot](./images/google-docs.png)

## google docs (document) - 46.57 MB

this seems like more than should be necessary. mainly js objects.

![memory-snapshot](./images/google-docs-document.png)

## google sheets (spreadsheet) - 96.98 MB

a lot of memory, especially considering spreadsheets were the killer app back in the apple 2
days, where lots of people brought computers for the first time to run visicalc on 64k of memory?

![memory-snapshot](./images/google-sheets-spreadsheet.png)

## hackmd (document) - 44.9 MB

about the same as a google doc

![memory-snapshot](./images/hackmd.png)

## sandstorm (spreadsheet) - 27.63 MB

almost 1/4 that of google spreadsheets.

![memory-snapshot](./images/sandstorm-sheet.png)

## toggl - 49.77 MB

time tracking software, quite bloated.

![memory-snapshot](./images/toggl.png)

## nytimes - 56.08 MB

very bloated.

![memory-snapshot](./images/nytimes.png)

## the guardian - 7.36 MB

pretty good.

![memory-snapshot](./images/the-guardian.png)

## the onion - 38.30 MB

quite bloated, nearly as much as reddit, but is created entirely by their in-house writers.

![memory-snapshot](./images/the-onion.png)

## open collective - 31.22 MB

react site, but it's not data that changes very often. pretty bloated.

![memory-snapshot](./images/open-collective.png)

## medium - 18.53 MB

could be better, but not as bad as others.

![memory-snapshot](./images/medium.png)

## medium (article) - 17.99 MB

![memory-snapshot](./images/medium-article.png)

## soundcloud - 22 MB

better than youtube

![memory-snapshot](./images/soundcloud.png)

## soundcloud (track open) - 45.80 MB

better than youtube

![memory-snapshot](./images/soundcloud-track.png)

## bandcamp - 14.86 MB

front page has listings, memory use similar to google search results.
the best content site.

![memory-snapshot](./images/bandcamp.png)

## bandcamp (album page) - 8.76 MB

pretty tight! MB

![memory-snapshot](./images/bandcamp-album.png)

## slack - 76.53 MB

bloated! largely javascript.

![memory-snapshot](./images/slack.png)

## rocketchat - 32.12 MB

does the same thing as slack, but with less javascript.
rocketchat is mostly js objects, but still less than rocketchat.

![memory-snapshot](./images/rocketchat.png)

## riot - 55.31 MB

more js objects than slack, but less javascript.

![memory-snapshot](./images/riot.png)

## talky - 9.40 MB

started a call with no one else in it. pretty tight!

![memory-snapshot](./images/talky.png)

## google hangouts - 10.76 MB

on a call by my self. also surprisingly unbloated!

![memory-snapshot](./images/hangouts.png)

## jitsi - 40.21 MB

4x google hangouts.

![memory-snapshot](./images/jitsi.png)

## meatspace chat - 4.48 MB

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

