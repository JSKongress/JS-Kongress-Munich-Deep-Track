# Technical SEO
by [Martin // @g33konaut](https://twitter.com/g33konaut/)

- Share state with hashes: It is always ignored. Do not use hash based routing as it's a hack.
- Googlebot: Over 130.000.000.000.000 URLs found.
- Crawl -> Processing -> Maybe rendering. The steps may be called "eventually". But it might take DAYS for pages that do
  not usually change that often.
- Dynamic rendering vs. static rendering: Google does not have to render always and get
  you in the index faster.
- When doing static rendering, you usually have the site faster in the index.
- Having JavaScript render the site or static html does not make a difference in ranking.
- Lighthouse should be a neutral thing. No Google specifics in there yet.
- Rendering time does not affect page rank or at least is only a tie-breaker
- Rendering: What JS version? Will it understand script modules?
  - Googlebot is using Chrome 41, Released 2015, 4 years old. Use ES5!
  - They want to create a infrastructure that catches up a lot quicker.
  - Puppeteer is a direct result of that effort
- How long will it wait for JS to finish / process JS?
  - Having title and descriptions the same on each page is a bad idea
- You can use g.co/mobilefriendly -> Check the HTML, what is going to be in there / indexed.
