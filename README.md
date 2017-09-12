# StreamFeeds
Creates an overlay of an RSS/Atom/etc. feed compatible with OBS

# Install
1. Put the rss.html file in a safe place.  I recommend making a new "Browser Overlays" directory in your OBS install directory.
2. Open rss.html with a text editor and change the list of RSS feeds to your liking.  
3. (optional) For advanced users consider changing the CSS and JS to meet your needs as well.
4. Open rss.html with a browser and ensure that it works the way you'd like.
5. Copy the URL out of the browser's address bar.
6. Create a new "Browser Source" scene asset in OBS and paste the URL into the address slot.

# Configuration
At the very top of the file, there is a list of RSS feeds that looks like:
var rss = [
  "https://twitchrss.appspot.com/vod/cobaltbluedw"
];

change this to your liking, adding and removing feeds, like:
var rss = [
  "http://www.reddit.com/r/news/.rss",
  "https://www.reddit.com/r/quotes/.rss",
  "https://twitrss.me/twitter_user_to_rss/?user=nerdist"
];

The JavaScript is designed such that most all the display and behavior is defined by the CSS.  For example, this block disabled many possible display elements:
.item-author, 
.item-category,
.item-summary,
.item-description,
.item-content {
  display: none;
}
If you know some CSS, you can completely change how your Feed looks/acts.

To change the amount of time between each feed item's display, find and change this line:
loadFeedRecursive(rss, 0, 30000);
30000 => is 30,000 milliseconds a.k.a. 30 seconds
change this value to your liking. e.g. 60000 would be 1 minute, 600000 would be 10 minutes, etc.
