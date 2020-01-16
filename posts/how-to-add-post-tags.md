---
title: How to Add Post Tags
excerpt: Overview of How Post Tags are Structured
published: false
date: 2020-01-16T05:13:05.024Z
tags:
  - templates
  - tag
---
Post tags are not only a handy way of loosely categorizing your content, but the functionality they provide to quickly pull up posts based on the tags themselves provides some additional navigation. 

In my hacked together setup, I did run into an issue where my post tags weren't showing in my PostCard.vue component or in my Post.vue template. Since the PostTags.vue component gets used in both places, this is where I started troubleshooting. 

This is what I had (copied from another repository) in my PostTags.vue template: 

![posttag.vue template](/uploads/tagtitle.png "PostTag.vue template. {{tag.title}} was wrong.")

I went back to my config.yml template to see what was going on.
