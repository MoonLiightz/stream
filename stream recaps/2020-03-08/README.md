# Stream #006 (2020-03-08)

**Main topic:** Turning the *simple Twitch bot* into a lib

## Topics

### Turning the *simple Twitch bot* into a lib

Between the last and this stream I had a private session/talk with [muesli/CodeCereal](https://github.com/muesli) who showed me some alternative ways to implement features. That led us to the current implementation of a channel (holding the events) as a return for the user who wants to use the library.
So far I did not mention that the *simple Twitch bot* is now more like a library which can be used by anyone. The implemetion for callback functions is yet gone but I will reimplement that in the future again. So in the end the user has the choice between a channel or function callbacks to work with events.

In the stream I worked on handling and parsing events like `PRIVMSG`, `JOIN` and `PART`. Channels, user, channel users etc. now have all own structs and the library holds an internal global userlist (`User struct`). Nearly no data is duplicated because of pointers.
I try to parse every message with simple splits to prevent the usage of regex. Regex is normally slow against simple splits.

## Lessons learned

Changing the structure of your data within Go code is super easy. Because as soon as you change types of your data the code breaks (obviously). If you use a proper IDE, every line that does not suit the definition gets marked red. So fixing these problems is extremely easy.

