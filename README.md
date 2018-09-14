# your web app is bloated

Using firefox's memory snapshot tool,
I measured the heap usage of a variety of web apps.
Here is how everything did.

App | Memory (MiB = 1024<sup>2</sup> B)
--- | ---:
google inbox |  215 (!!!)
gmail (standard) |  158
google sheets (spreadsheet) |  96.98
slack |  76.53
google-maps |  65.61
patchbay (patchlite) | 59.93
youtube video |  59.04
nytimes |  56.08
facebook messenger | 57.78
facebook newsfeed |  56.12
riot |  55.31
toggle |  49.77
google docs (document) |  46.57
soundcloud (track open) |  45.80
hackmd (document) |  44.9
reddit |  43.77
airbnb | 40.8
jitsi |  40.21
tweetdeck |  40.38
the onion |  38.30
rocketchat |  32.12
open collective |  31.22
vimeo (video) | 31.15
youtube |  30.00
sandstorm (spreadsheet) |  27.63
pinterest |  26.80
images.google (result) |  26.41
twitter |  25.09
google docs |  24.7
facebook |  23.49
soundcloud |  22
spotify | 19.64
medium |  18.53
medium (article) |  17.99
bandcamp |  14.86
google results |  14.77
patchless | 12.43
google-maps-mobile | 12.06
google |  11.30
google hangouts |  10.76
talky |  9.40
bandcamp (album page) |  8.76
dat-shopping-list | 8.28
gmail-mobile | 7.93
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

## Table of Contents

- [Method](#method)
- [Work](#work)
    - [github - 7.41 MB](#github---741-mb)
    - [google - 11.30 MB](#google---1130-mb)
    - [google results - 14.77 MB](#google-results---1477-mb)
    - [duckduckgo - 5.63 MB](#duckduckgo---563-mb)
    - [duckduckgo results - 4.81 MB](#duckduckgo-results---481-mb)
    - [google images (result) - 26.41 MB](#google-images-result---2641-mb)
    - [duckduckgo images (result) - 7.31 MB](#duckduckgo-images-result---731-mb)
    - [wikipedia - 1.73 MB](#wikipedia---173-mb)
    - [wikipedia (article) - 5.93 MB](#wikipedia-article---593-mb)
    - [stackoverflow - 2.55 MB](#stackoverflow---255-mb)
    - [google docs - 24.7 MB](#google-docs---247-mb)
    - [google docs (document) - 46.57 MB](#google-docs-document---4657-mb)
    - [google sheets (spreadsheet) - 96.98 MB](#google-sheets-spreadsheet---9698-mb)
    - [hackmd (document) - 44.9 MB](#hackmd-document---449-mb)
    - [sandstorm (spreadsheet) - 27.63 MB](#sandstorm-spreadsheet---2763-mb)
    - [toggl - 49.77 MB](#toggl---4977-mb)
- [Social / Comms](#social--comms)
    - [twitter - 25.09 MB](#twitter---2509-mb)
    - [tweetdeck - 40.38 MB](#tweetdeck---4038-mb)
    - [twitter (mobile) - 30.84](#twitter-mobile---3084)
    - [reddit - 43.77 MB](#reddit---4377-mb)
    - [facebook - 23.49 MB](#facebook---2349-mb)
    - [facebook newsfeed - 56.12 MB](#facebook-newsfeed---5612-mb)
    - [facebook messenger - 57.78 MB](#facebook-messenger---5778-mb)
    - [gmail (basic) - 0.81 MB](#gmail-basic---081-mb)
    - [gmail (mobile) - 7.93 MB](#gmail-mobile---793-mb)
    - [gmail (standard) - 158 MB](#gmail-standard---158-mb)
    - [google inbox - 215  MB (!!!)](#google-inbox---215--mb-)
    - [slack - 76.53 MB](#slack---7653-mb)
    - [rocketchat - 32.12 MB](#rocketchat---3212-mb)
    - [riot - 55.31 MB](#riot---5531-mb)
    - [meatspace chat - 4.48 MB](#meatspace-chat---448-mb)
- [video](#video)
    - [youtube (mobile) - 5.49 MB](#youtube-mobile---549-mb)
    - [youtube (mobile, playing video) - 15.94 MB](#youtube-mobile-playing-video---1594-mb)
    - [youtube - 30.00 MB](#youtube---3000-mb)
    - [youtube (video) - 59.04 MB](#youtube-video---5904-mb)
    - [vimeo (video) - 31.15](#vimeo-video---3115)
- [maps](#maps)
    - [google-maps - 65.61 MB](#google-maps---6561-mb)
    - [openstreetmap - 6.72 MB](#openstreetmap---672-mb)
    - [google-maps (mobile) - 12.06](#google-maps-mobile---1206)
- [news / content](#news--content)
    - [nytimes - 56.08 MB](#nytimes---5608-mb)
    - [the guardian - 7.36 MB](#the-guardian---736-mb)
    - [the onion - 38.30 MB](#the-onion---3830-mb)
    - [medium - 18.53 MB](#medium---1853-mb)
    - [medium (article) - 17.99 MB](#medium-article---1799-mb)
- [music](#music)
    - [soundcloud - 22 MB](#soundcloud---22-mb)
    - [soundcloud (track open) - 45.80 MB](#soundcloud-track-open---4580-mb)
    - [bandcamp - 14.86 MB](#bandcamp---1486-mb)
    - [bandcamp (album page) - 8.76 MB](#bandcamp-album-page---876-mb)
    - [spotify](#spotify)
- [video chat](#video-chat)
    - [talky - 9.40 MB](#talky---940-mb)
    - [google hangouts - 10.76 MB](#google-hangouts---1076-mb)
    - [jitsi - 40.21 MB](#jitsi---4021-mb)
- [other](#other)
    - [pinterest - 26.80 MB](#pinterest---2680-mb)
    - [airbnb - 40.8 MB](#airbnb---408-mb)
    - [open collective - 31.22 MB](#open-collective---3122-mb)
- [p2p](#p2p)
    - [patchless - 12.43 MB](#patchless---1243-mb)
    - [dat-shopping-list - 8.28 MB](#dat-shopping-list---828-mb)
    - [patchbay (patchlite) - 59.93](#patchbay-patchlite---5993)
- [conclusions](#conclusions)

## Method

I opened each site in firefox, and used the memory shapshot tool.
I screen shotted the output using `scrot`. I was running `ublock`,
and that probably made some sites smaller.

## Work

### github - 7.41 MB

github homepage (my news feed)

![memory-snapshot](./images/github.png)

### google - 11.30 MB

empty google page. A surprising amount of memory used since it shows nothing but a single field.

![memory-snapshot](./images/google.png)

### google results - 14.77 MB

prehaps still a lot of memory considering very little images or real time interactions here.

![memory-snapshot](./images/google-results.png)

### duckduckgo - 5.63 MB

much less memory than google! I guess it's the tracking features in google that uses the extra memory!

![memory-snapshot](./images/duckduckgo.png)

### duckduckgo results - 4.81 MB

![memory-snapshot](./images/duckduckgo-results.png)

### google images (result) - 26.41 MB

fairly efficient, compared to reddit, youtube etc

![memory-snapshot](./images/google-images.png)

### duckduckgo images (result) - 7.31 MB

1/3 the memory google images uses

![memory-snapshot](./images/duckduckgo-images.png)

### wikipedia - 1.73 MB

![memory-snapshot](./images/wikipedia.png)

### wikipedia (article) - 5.93 MB

static page with some images

![memory-snapshot](./images/wikipedia-article.png)

### stackoverflow - 2.55 MB

static site

![memory-snapshot](./images/stackoverflow.png)

### google docs - 24.7 MB

![memory-snapshot](./images/google-docs.png)

### google docs (document) - 46.57 MB

this seems like more than should be necessary. mainly js objects.

![memory-snapshot](./images/google-docs-document.png)

### google sheets (spreadsheet) - 96.98 MB

a lot of memory, especially considering spreadsheets were the killer app back in the apple 2
days, where lots of people brought computers for the first time to run visicalc on 64k of memory?

![memory-snapshot](./images/google-sheets-spreadsheet.png)

### hackmd (document) - 44.9 MB

about the same as a google doc

![memory-snapshot](./images/hackmd.png)

### sandstorm (spreadsheet) - 27.63 MB

almost 1/4 that of google spreadsheets.

![memory-snapshot](./images/sandstorm-sheet.png)

### toggl - 49.77 MB

time tracking software, quite bloated.

![memory-snapshot](./images/toggl.png)

---

## Social / Comms

### twitter - 25.09 MB

loaded twitter homepage and didn't scroll or touch anything

![memory-snapshot](./images/twitter.png)

### tweetdeck - 40.38 MB

twitter power user interface, with mentions and messages, one user's feed, and a search feed
added.

![memory-snapshot](./images/tweetdeck.png)

### twitter (mobile) - 30.84

not better than regular web twitter

![memory-snapshot](./images/twitter-mobile.png)

### reddit - 43.77 MB

the reddit homepage has an infinite scroller, usually means lots of javascript and js objects.

![memory-snapshot](./images/reddit.png)

### facebook - 23.49 MB

just the login page! already a lot of javascript has been loaded.
The most bloated landing page, twice as much as google, 10x wikipedia.

![memory-snapshot](./images/facebook.png)

### facebook newsfeed - 56.12 MB

a lot of objects are in memory, presumably this is from using react.

![memory-snapshot](./images/facebook-newsfeed.png)

### facebook messenger - 57.78 MB

same memory use as fb news feed. react, of course.

![memory-snapshot](./images/messenger.png)

### gmail (basic) - 0.81 MB

nearly nothing! I use this daily. Really, it's an amazing level of functionality and user-friendlyness,
packed into a very simple interface. Also, because it doesn't have any
kind of dynamic updates, it's less distracting than the other email interfaces. You have to
intentionally check for emails, there is no notifications or changing favicons. so ugly it's beautiful.

![memory-snapshot](./images/gmail-basic.png)

### gmail (mobile) - 7.93 MB

Google's mobile apps are respectable.
again, pretending to be a nexus 5.

![memory-snapshot](./images/gmail-mobile.png)

### gmail (standard) - 158 MB

amazingly bloated. mostly massive amounts of javascript (it has a progress bar that shows at startup)
but just the JS objects are 37 mb.

![memory-snapshot](./images/gmail-standard.png)

### google inbox - 215  MB (!!!)

makes standard gmail look tame. did they take gmail standard and just add more stuff?

![memory-snapshot](./images/google-inbox.png)


### slack - 76.53 MB

bloated! largely javascript.

![memory-snapshot](./images/slack.png)

### rocketchat - 32.12 MB

does the same thing as slack, but with less javascript.
rocketchat is mostly js objects, but still less than slack.

![memory-snapshot](./images/rocketchat.png)

### riot - 55.31 MB

more js objects than slack, but less javascript.

![memory-snapshot](./images/riot.png)

### meatspace chat - 4.48 MB

as tight as a static site, but does crazy javascript stuff!

![memory-snapshot](./images/meatspace-chat.png)

---

## video

### youtube (mobile) - 5.49 MB

just the landing page. acceptable.

![memory-snapshot](./images/youtube-mobile.png)

### youtube (mobile, playing video) - 15.94 MB

![memory-snapshot](./images/youtube-mobile-video.png)

### youtube - 30.00 MB

pretty light weight considering it's youtube

![memory-snapshot](./images/youtube.png)

### youtube (video) - 59.04 MB

At first I thought this was reasonable (since you are playing video)
but then I discovered that actually you can play video with a lot less!

![memory-snapshot](./images/youtube-video.png)

### vimeo (video) - 31.15

![memory-snapshot](./images/vimeo.png)

## maps

### google-maps - 65.61 MB

Pretty heavy compared to the other options.
I've been informed that this uses webgl, but the mobile version only uses tiles.

![memory-snapshot](./images/google-maps.png)

### openstreetmap - 6.72 MB

only 10% the memory of google maps and does essentially the same thing!

on new york, with transportation layer enabled

![memory-snapshot](./images/openstreetmap.png)

### google-maps (mobile) - 12.06

pretending to be a nexus 5. Much better!
you can also force this version by adding `?force=pwa` to [google-maps url](https://maps.google.com/?force=pwa)

![memory-snapshot](./images/google-maps-mobile.png)

---

## news / content

### nytimes - 56.08 MB

very bloated.

![memory-snapshot](./images/nytimes.png)

### the guardian - 7.36 MB

pretty good.

![memory-snapshot](./images/the-guardian.png)

### the onion - 38.30 MB

quite bloated, nearly as much as reddit, but is created entirely by their in-house writers.

![memory-snapshot](./images/the-onion.png)

### medium - 18.53 MB

could be better, but not as bad as others.

![memory-snapshot](./images/medium.png)

### medium (article) - 17.99 MB

![memory-snapshot](./images/medium-article.png)

---

## music

### soundcloud - 22 MB

better than youtube

![memory-snapshot](./images/soundcloud.png)

### soundcloud (track open) - 45.80 MB

better than youtube

![memory-snapshot](./images/soundcloud-track.png)

### bandcamp - 14.86 MB

front page has listings, memory use similar to google search results.
the best content site.

![memory-snapshot](./images/bandcamp.png)

### bandcamp (album page) - 8.76 MB

pretty tight!

![memory-snapshot](./images/bandcamp-album.png)

### spotify

Impressive!

![memory-snapshot](./images/spotify.png)

---

## video chat

### talky - 9.40 MB

started a call with no one else in it. pretty tight!

![memory-snapshot](./images/talky.png)

### google hangouts - 10.76 MB

on a call by my self. also surprisingly unbloated!

![memory-snapshot](./images/hangouts.png)

### jitsi - 40.21 MB

4x google hangouts.

![memory-snapshot](./images/jitsi.png)

## other

### pinterest - 26.80 MB

about the same as google images

![memory-snapshot](./images/pinterest.png)

### airbnb - 40.8 MB

Searched for "san francisco". A lot of memory used to just display a list,
especially considering there is no map displayed. Smells like react.

![memory-snapshot](./images/airbnb.png)

### open collective - 31.22 MB

react site, but it's not data that changes very often. pretty bloated.

![memory-snapshot](./images/open-collective.png)

--

## p2p

### patchless - 12.43 MB

A [social p2p client](http://github.com/patchless/patchless) with heavy javascript, including infinite scrollers!

![memory-snapshot](./images/patchless.png)

### dat-shopping-list - 8.28 MB

simple [shopping list app on dat](https://dat-shopping-list.glitch.me/)

![memory-snapshot](./images/dat-shopping-list.png)

### patchbay (patchlite) - 59.93

slightly old version of [patchbay](https://github.com/ssbc/patchlite) because it could be bundled and run inside firefox.

![memory-snapshot](./images/patchbay.png)

## conclusions

I started exploring this because I was trying to figure out how to optimize my own apps.
Memory use isn't the most important thing, but it is an easy to measure proxy. If you have
less memory usage, you probably have a simpler app, which is probably more performant.
Less memory also means lees garbage collection activity.

google's apps are particularly interesting because they provide both the worst offenders
(gmail, inbox, docs), but their mobile apps are really solid!

Recently, web development style has moved towards a fully dynamic front end that generates
everything in javascript. If a app really is highly dynamic, I guess that is somewhat excusable,
(such as facebook or slack) but I on a site that could be static it obviously uses a lot more.

I think this just shows there is considerable room for improvement in terms of application efficiency.
