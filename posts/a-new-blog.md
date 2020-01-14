---
title: timeToRead
excerpt: timeToRead custom field built into Gridsome
published: true
date: 2020-01-13T20:27:15.612Z
cover_image: ''
---
One of the fields I noticed when setting up Netlify CMS was `timeToRead`.

Here it is in a PostMeta.vue component, which is part of the PostCard.vue component: 

![PostMeta.vue component inside the gridsome-starter-blog](/uploads/timeToRead.PNG "PostMeta.vue")

Apparently, this is [built into Gridsome](https://community.netlify.com/t/netlify-cms-gridsome-timetoread-custom-field/1751/2) and is "based on **230 words per minute** in Gridsome", which explains why it doesn't appear in my Netlify CMS admin panel or `config.yml` but can be queried and generated on my site.
