# TH_RADIO
First things first. This repository is not about an actual app that is available for download at any appstore whatsoever.
It is about being creative, learning something new and making use of informationen provided in a way originally not meant nor intended to.
Yes, you're right: It's about hacking - in some sorts.

# Disclaimer
When studying this repository, you will of course notice that it actually _is_ an app. So what is this all about anyway?
It is also about the love for radios that drive me and the love for finding creative solutions to problems noone else experiences.
In this case: It's about an internet queue based radio that you only have access to under specific circumstances and that you can only get information about what's Now Playing via archaic means. That is: There's actually no way of just streaming this radio station on your phone and know what you are actually listening to. 

Or is there?

Even if it is, I would get banned if I released any kind of app related to this radio on the stores. 
So I won't. 

Also, you wouldn't be able to use this program anyway if you were not eligible for it. 
That means: Don't do that at home.

# Background information
If you read until here, you might already know that I am talking about Telehack.com. 
In case you already have an account on this network, read on, if not: Go get one by telnetting into telehack.com on port 23.
You might already noticed that there is a queue based radio station operated by Telehack that you can tune into once you have the ACCT status and that you are able to queue own requests once you reached the REGUSER status.
At that point you might want to listen to Telehack Radio even on the road and wonder why there's no app available.
The reason is simple: Because.

Well. This, and the fact that "MAY THE COMMAND LINE LIVE FOREVER".
And an app is just no commandline.
Or... could it be?

Here's the thing: There is no known API that you could make calls to to retrieve Now Playing information about title, artist, song length, etc.
The only (known) way to get this information is logging into Telehack and using the commandline. 
And since Telehack is about hacking, people can not only watch over your shoulder and see what you're doing, it also becomes part of a - let's say - global log, people can follow live.
That means, that even if there was some sort of app that tunes into Telehack Radio and silently logs into your account via telnet automatically triggering commands for extracting Now Playing information, this process would flood the respective logs for no good. 
This is to be prevented by all means.

# Goals
The following list is a rough summary of features to be implemented to create a comfortable commandline experience that allows for listening to and interacting with the Telehack Radio even when you're away from your desktop computer and/or currently not (really) logged into Telehack. 

- Create a crossplatform base app using Microsoft .NET MAUI
- Add a configuration that allows for streaming audio from telehack.com
- Add a configuration that allows for background audio streaming
- Add an invisible MediaElement control and make it stream Telehack Radio
- Add the possibility of configuring the users' account in Telehack style (SET)
- Add the possibility of configuring whether to use telnet (username/password) or SSH (private key)
- Add command structure that allows for logging into the users' Telehack account
- Add a vanity check to make sure, the user has the appropriate status (ACCT, REGUSER)
- Add a check that makes sure, the users' activities are hidden from the global log
- Add command structure that allows for collecting viable information about Telehack Radio (such as title, artist, etc.)
- Add a parser that transforms the servers' response into an object structure that can be bound to the user interface
- Add a user interface that shows Now Playing information in a command line way, optimized for the respective display resolution
- Add a commandline compatible progress bar with information about the current song position and how much is left to play
- Add code that only triggers collecting information when necessary (i.e. the current song came to an end) so that the system is not flodded with commands unneccessarily
- Add an Audio Level Analyzer that is able to find out whether there is some music streaming going on
- Add logic code that disables commands being sent when there is nothing being streamed and only enables this feature when the Audio Level Analyzer gives positive feedback
- Add a commandline style interface that allows for queueing own requests
- Add other commands as well such as dequeueing or retrieving information about other users listening
- Add the possibility to retrieve cover art for the song currently being played
- Add an ASCII-Art generator for transforming found cover art to commandline compatible ASCII and show it in the user interface
- Add Live-Show compatibility
- Add QOTD-Feature - just for fun

  
