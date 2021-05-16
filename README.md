# Twitter-Bot
Keep on track with your favorite Twitter accounts and redirect their tweets to your WhatsApp number if you are as lazy as me and don't open Twitter on a regular basis.
In this example I redirect all Tweets of Elon Musk to my WhatsApp number.

# How to use
0. Install node.js if needed: https://nodejs.org/en/download/
1. Create a dev account for the twitter API if you don't already have one: https://developer.twitter.com/en 
2. Register your WhatsApp number on callmebot.com (cmb): Follow: https://www.callmebot.com/blog/free-api-whatsapp-messages/
3. Insert your Twitter API keys and cmb key in the data/data.json
4. Run "node bot.js"

# Customize bot.js
The bot makes a request to the Twitter API every 10 seconds.
customize here (millis) 
```javascript
    setInterval(main, 10000);
```

If you want to look for other accounts etc:
Go to bot.js -> check the getTweets() function
Adjust the params object

Look for an account name and get the last 2 tweets (if the bot runs 24/7 it's not necessay to get more than 2 tweets per cicle)

```javascript
        let params = {
            from: 'elonmusk',
            count: 2
        };
```

Look for a hashtag and get the last 10 tweets

```javascript
        let params = {
            q: '#funstuff',
            count: 10
        };
```

#Note
All tweets get collected into one message sent by cmb due to cmb only allowing 25 messages per 240 minutes.
If this changes some day, you could also send every tweet in one message.

In the params.json the id of the last tweets gets saved to not redirect the same tweet multiple times.

# Sources
Check out for basic understanding of the Twitter API: Level Up Developer: https://www.youtube.com/watch?v=0gFzUYSbJwY
Used for WhatsApp connection: https://www.callmebot.com/blog/free-api-whatsapp-messages/
