---
title: "4D_web_scrapping_1"
date: 2021-06-25T16:44:25+08:00
---

As I mentioned earlier, I was embarking on my side project (in efforts to improve my JS knowledge). I want to consolidate all our Malaysia's 4D gaming results into a single hosted app. Thus I needed to find the sources. I know that there are 3 major betting company players:

1. Damacai
2. Magnum
3. Sports Toto

Of the 3, both Magnum and Damacai has APIs which I can use. Of these 2, Magnum API is pretty straightforward. But Damacai's was a little trickier but can be obtain.

As for Sports Toto's, I had some initial problem finding API. Using DevTools I was not able to find any API get requests anywhere, thus I decided to using some MITM (man-in-the-middle) technique to see if they had their API calls via their android application. Now even having done that, I was not able to find any API request via the wire. This means that the data rendering is clearly done on the server side and the html tables or list was already rendered before sending down the whole html response to the client. Which means that API is definitely not a way to go with Toto's webiste. I had no choice but to use a scraper / crawler for it.

What scraper to use?

At first I was using scrapy which is a python based scarping framework. I liked it because it comes with all the bells and whistle. Once you downloaded the library, it has settings.py, config.py and much more which one can leverage on. Its also neatly and thoughtfully had all these features structured nicely for the user to implement their robot for its crawling or scraping needs. Even has the items for outputing captured data in a nice object notation form. But scrapy was acting weird for me because it seems that when the webpage was ingested into the internal object, some additional tags (\\t, \\n, and \\r) were injected into it thus rendering my xpath calls useless.

After trying countless times, I decided to swith to puppeteer which is Google's javascript based scraping framework. Love it immediately. Compared to scrapy, there's less documentation and help/ resources, but that's quickly going to change. I see lots of people adopting puppeteer and its also extremely powerful and quick. I didn't have those additional tags being injected mid-stream when running the code, thus my queryselectors and xpaths all just works!!!

I've my initial scraping in my github js4dscrapper repository. And its still a work in progress.

Next up is to work on my APIs for the other 2 players.
