# Stream #007 (2020-03-12)

**Main topic:** Finalizing Twitch lib

## Topics

### Finalizing Twitch lib

I really thought I could finalize the Twitch library in this stream but then I stumbled over the `USERNOTICE` event. It's the, as far is I currently know, the most complicated event that could happen within the IRC protocol. It covers the following child events:

- sub
- resub
- subgift
- anonsubgift
- submysterygift
- giftpaidupgrade
- rewardgift
- anongiftpaidupgrade
- raid
- unraid
- ritual
- bitsbadgetier

After a couple of minutes it was clear to me that I can not handle all child events just as a `USERNOTICE` event in the library. Almost every child event has specific attributes and it would only be fair if the library user can separately react on them.
For the stream I simply wrote every attribute in the `USERNOTICE struct` but is has to be refactored (and will be).

You shouldn't be surprised if you may already looked into the [learning-go-twitch-bot](https://github.com/curi0s/learning-go-twitch-bot) and didn't see the commit of this stream. Offstream I actually decided to turn it in a library and named it [Twirgo](https://github.com/curi0s/twirgo). Anyway you should follow this repo :grin:.

## Unexpected/Problematic things

As already described in the topics the `USERNOTICE` event is huge and covers multiple child events.
