# Stream #005 (2020-03-05)

**Main topic:** Build simple Twitch bot with Go

## Topics

### Build simple Twitch Bot with Go

After I made it successfully through the [Go tour](https://tour.golang.org/welcome/1) it was time to apply this knowledge and develop something. I thought it would be a great use case to develop a chat bot for either Discord or Twitch.
I also think that if you learn(ed) a new language you should develop something from scratch and do not simply use a library someone wrote. To follow my own advice I started with a Twitch bot because handling the IRC protocol is much easier than working with the websocket of Discord.

Here is a list of things I did (the [commit](https://github.com/curi0s/learning-go-twitch-bot/commit/77bbcbc3fe40a780bf09a9df15972b012f9dd869) is also available):

1. Connecting to irc.chat.twitch.tv:6667 via TCP
2. Defining channels for sending and receiving messages/commands
   1. Sending authentication via `PASS` and `NICK` commands
   2. Also respond to `PING` protocol events
3. Adding callback methods for `onConnect` and `onMessage` events

## Other stuff

Using Go makes a lot of fun. If you understand the most slides of the [Go tour](https://tour.golang.org/welcome/1) and remember them while writing code, than it should be fairly easy for you imho.

> Even though I have to mention that I got and get **a lot** of help from [muesli/CodeCereal](https://github.com/muesli).

