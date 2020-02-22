# Stream #1 (2020-02-15)

**Main topic:** Creating a Twitch bot for the tech streams

It was the first tech stream with quite some problems regarding freezes of the hackintosh and memory leaks + crashes of OBS. More in [Unexpected/Problematic things](#unexpectedproblematic-things).

## Topics

### Twitch bot

We started and also finished the Twitch bot for the tech stream. The [repository](https://github.com/curi0s/twitch-bot) is also public available.
I planned to add a bunch of commands for the beginning:

- !vscode
- !extensions
- !repository
- !hackintosh
- !job
- !theme
- !today
- !social

We searched for some libraries we could use for either nodejs or Python. The library for nodejs seemed really well documented but I still think JavaScript in the backend is something that shouldn't be possible :sweat_smile:. Why? I try to explain my perspective in [other stuff](#other-stuff). In the end we or rather I chose a Python library named [TwitchIO](https://github.com/TwitchIO/TwitchIO).
After reading the README.md I realized that I used it already in the past but had some problems with stability and persistent connection to the chat (TMI of Twitch). But it shouldn't be a problem in this case because the bot will only run if I work on the hackintosh (even if I don't stream). So this bot will not run 24/7. Using TwitchIO reminds me a lot of using [discord.py](https://github.com/Rapptz/discord.py) for Discord bots.

## Unexpected/Problematic things

### Crashes

#### Memory leak

OBS had a quite ridiculous memory leak caused by a countdown with a specific font (yes...). We are talking about 126 GB of ram usage. Yes the hackintosh has "only" 16 GB of physical ram but I don't know how much swap Mac OS provides by default or how the hell this was even possible. I do not have any screenshots of the message but it was a funny moment in the stream after I saw/discovered the 126 GB usage.

So this is fixed :heavy_check_mark:
> As of 2020-02-22, this is **NOT** fixed and happens randomly. One thing I could discover was, that I should always automatically deactivate the source of the countdown to prevent it from being loaded. Can be configured by check an option on the browser source to unload it if isn't visible.

#### OBS crashes

Two or three times while I streamed OBS crashed. It just closed and I did not get any message. To be honest, I did not look into any logs that maybe exist by now. It's now a todo in the [TODOs file](../../TODO)

Not fixed :x:

#### Freezes

The biggest problem of the stream were the two (or maybe three) freezes I encountered. Suddenly while I worked on something the whole hackintosh froze and the only thing I could do was to hard reset.
A moment I remember quite well was a click on a link in the chat (Twitch clip). I don't think Twitch was the problem in this case, it must have been something else.
While I stream, I also use my TV which is wall mounted above my main monitor as a second screen for OBS, chat and events (like subs). Maybe this setup (a second screen) in combination with OBS causes this problem. In the next stream I am going to try to stream only with my main monitor to exclude this theory.

Not fixed :x:
> In the stream of 2020-02-21 I did not encounter a freeze or crash, but I can not safely say that the second monitor is the root cause.

## Lessons learned

I actually don't know if there is really something new I or we learned in this stream. Half of the stream was trying to figure out what causes freezes, crashes and/or leaks and in the end to change a font in the countdown isn't something I would say is necessary to know 🤔.

> (Which didn't even really solve the problem - 2020-02-22)

## Other stuff

### JavaScript (nodejs) in the backend

I'm a little bit older, 32 at the creation of this file. I started with HTML at around 12 and just a little bit later with CSS, JavaScript and PHP.
At this time JavaScript was just the thingy in the frontend for some rudimentary animations and even if you used it, you had to make sure that the website works absolutely the same even **without** JavaScript.
You maybe ask yourself now why this was necessary. JavaScript was often deactivated by default or the user deactivated it for security reasons. Don't get me wrong I don't think JavaScript has or causes more vulnerabilities than other languages but I still think it should stay in the frontend. I also think that SPAs (Single Page Applications) are actually a really great technique to move the complete view to the client.
JavaScript, the cool thing in the frontend for animations (yeah I know, CSS3) and _many_ asynchronous calls to lazy load data.
