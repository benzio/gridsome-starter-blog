---
title: My First Post—Long Overdue
excerpt: 'Finally, I have a working Gridsome site with Netlify CMS.'
published: true
date: 2020-01-13T18:25:32.904Z
cover_image: /uploads/shutterstock_1590313948.jpg
---
I have resolved myself to writing this post, whether I like it or not. Whether it's good, or not. I've been working on the setup for this blog for about five hours now over the past three days, and I've finally reached the point where I can log into my Netlify CMS admin panel, publish a post, and have it display correctly on this site. 

You may think this isn't that big of a deal, and for a developer, it's not. For someone who knows how to work with the data, troubleshoot the build errors, get fields to correspond between the settings and templates, it's not a big deal at all. 

But for me, someone who has no idea what they are doing? Yes. It's a big deal. Finally, it works.

## Why a static site? And why Gridsome?

I first became enamored with static sites a little over a year ago when, in my day-to-day responsibilities working with WordPress administration and optimization, I was getting tired of slow page loads and the general headaches associated with ongoing WordPress maintenance. "There has to be a better way," I thought. 

This is when I discovered [Gatsby](https://www.gatsbyjs.org/). Despite the steep learning curve (having only really worked with WordPress and php, and knowing nothing about JAM stack), Gatsby seemed to be exactly what I needed. After several weeks of installing and working with different [starters](https://www.gatsbyjs.org/starters/), creating and modifying components and templates, I kind of dropped it. React was kind of a pain to work with and presented a steeper learning curve than I wanted to handle. 

After a couple of months, when I revisited my Gatsby projects, I began to research other static site generators. [Pelican](https://blog.getpelican.com/), [Hugo](https://gohugo.io/) and [VuePress](https://vuepress.vuejs.org/) all kind of caught my eye, but for some reason, Gridsome looked the most appealing. I read somewhere that Gridsome was like Gatsby but used [Vue.js](https://vuejs.org/) instead of React. This is oversimplifying a bit, but I've found working with Vue.js in Gridsome is a lot easier than the React components in Gatsby, so Gridsome became my generator of choice. 

## Why Netlify CMS?

I've wavered back and forth about whether I need a CMS at all? Certainly not for a simple blog like this. I could probably just get away with using a simple text editor and uploading my posts to my repository and call it a day. I was even able to get a simple workflow going on iOS with [WorkingCopy](https://workingcopyapp.com/) and [iA Writer](https://ia.net/writer) over the weekend, which was much easier than getting Netlify CMS wired up to this site. The iA Writer app even has a nice little [Markdown guide](https://ia.net/writer/support/general/markdown-guide) to help get you started. 

However, the main goal of implementing Netlify CMS wasn't for this blog. The purpose of this blog is a testing ground for a different work-related Gridsome installation that features a blog with multiple authors. I don't know the authors. I don't know if they know markdown. I don't know anything. They may not know anything, so a simple CMS is in order. 

I do have a separate personal blog that uses [Forestry](https://forestry.io/), but after working with a few different installations, I now approach these projects with a template-first mindset. While learninand the [template I used](https://github.com/LokeCarlsson/gridsome-starter-bootstrap) required the least amount of development work to get off the ground. A CMS would have to come later. 

Netlify CMS seems to be the most common CMS to use with Gridsome and it looks like it has the most support (albeit not much for Gridsome, but it has plenty of support for other static site generators). I guess I could've gone through the painstaking steps of using my Forestry starter as a guide to implementing it on this site, but after trying to implement Netlify CMS a few times, it became kind of a personal challenge, so I just had to go with it. 

## The challenges connecting Netlify CMS

There were really only two major hurdles in getting this cms off the ground: the first being I was left at the mercy of the [Gridsome guide](https://gridsome.org/docs/guide-netlify-cms/) and was really working without any kind of template; the second being it was kind of a pain fixing the build errors, and there were several. However, once I looked at a few of the build errors, I could see a pattern and they became much easier to pinpoint. 

### Challenge one: working from scratch

It's always much easier to begin with a template or starter rather than building something from scratch, which is how I originally wanted to approach this project. However, the docs kept telling me it was really easy so I followed the guide, word-for-word, but I ran into build issues with core-js version 3. Apparently, core-js was upgraded to version 3, but some things still use core-js version 2 (babel?), so I went ahead and installed it.

Next, I forked [this starter](https://github.com/mittalyashu/gridsome-starter-netlifycms), which worked right away. However, it didn't have any style. I decided rather than modifying the templates, and spending time modifying the css, which would take me way longer than wiring up the cms, I'd use this repository as a guide for setting it up on my own starter blog. 

I copied the contents from the `config.yml` and the `<page query>` and began to modify to fit my schema. 

(*Note: and now that I've done a bit more thorough searching, I probably should have forked this repository: <https://github.com/suits-at/netlifycms-gridsome>. However, it still probably would require core-js version 2. At any rate, I finally got something working. )

### Challenge two: troubleshooting the build errors

This wasn't the biggest pain I've ever had setting up a website, but I was making it way more complicated than it should have been. 

I knew it wasn't going to magically work after the initial setup, but I was getting a little frustrated with a couple of the build errors in the `page query` on the index and post templates. 

In the Netlify `config.yml`file, you have a set of collections with field labels. These field labels need to correspond to the fields you query in your templates. So, for example, if you have a configuration file with the following fields: 

`fields:`

`- {label:"Title",name:"title",widget:"string"}`

`- {label:"Excerpt",name:"excerpt",widget:"string"}`

`- {label:"Publish Date",name:"date",widget:"date"}`

`- {label:"Body",name:"body",widget:"markdown"}`

then you need to make sure you are querying only those fields in your templates in order for your site to pull your blog entries into the blogroll. 

`<page-query>`

`query {`

`posts: allPost (filter: { published: { eq: true }}) {`

`edges {`

`node {`

`id`

`title`

`date (format: "D. MMMM YYYY")`

`cover_image`

`timeToRead`

`excerpt`

`path`

`tags {`

`id`

`path`

`}`

`}`

`}`

`}`

`}`

`</page-query>`

The other issue I had troubleshooting was the `allPost (filter: { published: { eq: true }})`, which was resolved relatively quickly by adding a `published` field to my `config.yml` file and refreshing my browser after updating. Since Netlify CMS doesn't have a draft mode, this filter at least gives you the option of only pulling any post where the published field = yes. 

### Moving forward

I really don't know if the core-js version is that big of a deal, but I'll keep rolling with it until something breaks. Fingers crossed!
