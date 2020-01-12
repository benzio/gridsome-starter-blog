---
title: Issues connecting Netlify CMS
date: 2020-01-11
published: true
tags: ['Markdown', 'CMS', 'Setup']
series: false
cover_image: ./images/human-fist-163431.jpg
canonical_url: false
description: "Connecting this site to Netlify CMS isn't difficult. However, there are issues with core-js on build."
---

One of the drawbacks for a non-developer like me with Gridsome (or any other static site generator) are build fails. I hate build fails. Build fails bring me face to face with my own ignorance and lack of skill. 

Fortunately, I've been working with the Github--deploying to Netlify--long enough now that they no longer induce the physical displays of anger of endeavors past. However, they’re still annoying as hell. I just want things to work (don’t we all?). 

Connecting this 
[Gridsome Starter Blog](https://gridsome.org/starters/gridsome-blog-starter/) to Netlify CMS, the build fails each time due to a discrepancy with core-js version. There were no 

I was able to find some related issues with Gatsby, and found that downgrading the core-js to an earlier version fixed the problem...almost an hour later.

## Issues logging in

There were also some hiccups with the Netlify CMS login process. Working from a local copy was kind of a pain.
