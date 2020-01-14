---
title: timeToRead
excerpt: timeToRead custom field built into Gridsome
published: true
date: 2020-01-13T20:27:15.612Z
cover_image: ''
---
One of the fields I noticed when setting up Netlify CMS was `timeToRead`.

Here it is between my query tags in index.vue:

```v
<page-query>
query {
  posts: allPost (filter: { published: { eq: true }}) {
    edges {
      node {
        id
        title
        date (format: "D. MMMM YYYY")
        cover_image
        timeToRead
        excerpt
        path
        tags {
          id
          path
        }
      }
    }
  }
}
</page-query>
```

Apparently, this is [built into Gridsome](<`allPost (filter: { published: { eq: true }})`>) and is "based on**230 words per minute** in Gridsome", which explains why it doesn't appear in my Netlify CMS admin panel or `config.yml` but can be queried and generated on my site.
