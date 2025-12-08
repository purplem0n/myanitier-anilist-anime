# myanitier-anilist-anime
Full json data of anime list from Anilist for myanitier usage containing around 21000+ entries.

## Why not just call the graphql API?
Anilist's API only returns 50 items per page when filtering/searching anime, if we put this into practice with a Tier Maker app, the UX will be very clunky as the user will have to paginate to find the entry they are looking for. To make it simplier, MyAnitier just scrape the entire anime list from anilist and let the client app download all anime in one download url call with client side caching. This also prevents overloading the Anilist API server because recently they actually degraded into lower rate limits. So instead of each user calling the Anilist API, everything is offloaded into the client-side downloaded anime list.

## How often does this json data get Updated?
- Every 24 hours
- The cron job performs around 400 api calls (50 items per page, 20000+ anime entries)
- This number of api call within 24hrs is very low and should not overload the server
