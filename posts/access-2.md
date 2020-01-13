---
title: My First Post—Long Overdue
excerpt: 'Finally, I have a working Gridsome site with Netlify CMS.'
published: true
date: 2020-01-13T18:25:32.904Z
cover_image: /uploads/shutterstock_1590313948.jpg
---
I have resolved myself to writing this post, whether I like it or not. Whether it's good, or not. I've been working on the setup for this blog for about five hours now over the past three days, and I've finally reached the point where I can log into my Netlify CMS admin panel, publish a post, and have it display correctly on this site. 

You may think this isn't that big of a deal, and for a developer, it's not. For someone who knows how to work with the data, troubleshoot the build errors, get fields to correspond to each other between the settings and templates, it's not a big deal at all. 

But for me? Yes. It's a big deal. 

## Why a static site? And why Gridsome?

I first became enamored with static sites a little over a year ago when, in my day-to-day responsibilities working with WordPress administration and optimization, I was getting tired of  slow page loads and the general headaches associated with ongoing WordPress maintenance. "There has to be a better way," I thought. 

<iframe src="https://giphy.com/embed/xT1R9VfCZAedFGAOYg" width="480" height="270" frameBorder="0" class="giphy-embed" allowFullScreen></iframe><p><a href="https://giphy.com/gifs/sharktank-shark-tank-917-xT1R9VfCZAedFGAOYg">via GIPHY</a></p>

This is when I discovered [Gatsby](https://www.gatsbyjs.org/). Despite the steep learning curve (having only really worked with WordPress/php and knowing nothing about JAM stack), Gatsby seemed to be exactly what I needed. After several weeks of installing and working with different [starters](https://www.gatsbyjs.org/starters/), creating and modifying components and templates, I kind of dropped it. React was kind of a pain to work with and presented a steeper learning curve than I wanted to handle. 

After a couple of months, when I revisited my Gatsby projects, I began to research other static site generators. [Pelican](https://blog.getpelican.com/), [Hugo](https://gohugo.io/) and [VuePress](https://vuepress.vuejs.org/) all kind of caught my eye, but for some reason, Gridsome looked the most appealing. I read somewhere that Gridsome was like Gatsby but used [Vue.js](https://vuejs.org/) instead of React. This is oversimplifying a bit, but I've found working with Vue.js in Gridsome is a lot easier than the React components in Gatsby, so Gridsome became my generator of choice. 

## Why Netlify CMS?

I've wavered back and forth about whether I need a CMS at all? Certainly not for a simple blog like this. I could probably just get away with using a simple text editor and uploading my posts to my repository and call it a day. I was even able to get a simple workflow going on iOS with [WorkingCopy](https://workingcopyapp.com/) and [iA Writer](https://ia.net/writer) over the weekend, which was much easier than getting Netlify CMS wired up to this site. The iA Writer app even has a nice little [Markdown guide](https://ia.net/writer/support/general/markdown-guide) to help get you started. 

However, the main goal of implementing Netlify CMS wasn't for this blog. The purpose of this blog is a testing ground for a different work-related Gridsome installation that features a blog with multiple authors. I don't know the authors. I don't know if they know markdown. I don't know anything. They may not know anything. So a simple CMS is in order. 

I do have a separate personal blog that uses [Forestry](https://forestry.io/), but I always approach these projects with a template-first mindset, and the [template I used](https://github.com/LokeCarlsson/gridsome-starter-bootstrap) required the least amount of development work to get off the ground. A CMS would have to come later. 

Netlify CMS seems to be the most installed CMS with Gridsome and it looks like it has the most support. I guess I could've gone through the painstaking steps of using my Forestry starter as a guide to implementing it on a different site, but since there is the most information out there about Netlify CMS, my decision was made.
