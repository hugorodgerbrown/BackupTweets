h2. What is this?
It's a very simple AppEngine application that can be used to download a user's public tweets (no DMs).

Why bother - loads of sites do that?
Yes, they do - but they all do other stuff as well - they'll stick the feed in your calendar, draw animations, Tweet on your behalf - and whole bunch of other stuff that is probably really cool, just not right now. I wanted to simply download my Tweets (so I could search them offline) - that's all.

So how does it work?
First off, the Twitter API only gives access to your last 3,200 tweets, so if you're over that, and you want to go back further you're out of luck. Now that's out of the way I'll explain how it works. It's blindingly simple - it calls the public Twitter API repeatedly, downloading page after page until it runs out of steam. The API supports both XML and JSON, so I will too. Eventually. Or maybe you will - it's Open Source, right?

For now, I really don't need the entire tweet (http://www.scribd.com/doc/30146338/map-of-a-tweet) - I just want the date and content. I do want my retweets, but fortunately that's just a querystring parameter, so I'll get them anyway. In simple terms, this application downloads each page of tweets, extracts the timestamp and content (the Tweet itself), and stores in the data store. It can then be downloaded as a CSV.

Anything else I should know?
This service will NOT download DMs - that would require OAuth integration, and I can't really be bothered.

Should I be worried about you stealing my data?
No - it's public anyway - that's the point. I'm just making it easier for you to get at it.

I have a great idea / I really want more information:
If you know how AppEngine works - go for it - you are feed to fork and conquer.
If you want to get hold of me - I'm @hugorodgerbrown.

If you want to see the full Twitter API in action - I suggest you visit Apigee, who have an excellent API console here - http://app.apigee.com/console/twitter