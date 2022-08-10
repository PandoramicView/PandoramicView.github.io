---
title: "Site Update!"
excerpt: "tldr; comments, my dude!"
categories:
  - website
tags:
  - Jekyll
  - site update
  - hobbies
  - site
  - routine
---
## Comments

![image-center](https://64.media.tumblr.com/99a29dd99312cf6b3ddc987cecc3d2a2/tumblr_p2py6fRJjr1qge1sho1_400.gifv){: .align-center}

Actually a huge pain in the ass to set up, as a person who is only moderately technical. For someone who's comfortable and familiar with the languages and structures, I imagine it wouldn't be terrible, though. I'm using [Staticman](https://staticman.net/) because I'm a fan of not requiring anyone to sign up for some kind of account, and my [jekyll](https://jekyllrb.com/) [theme](https://mmistakes.github.io/minimal-mistakes/) already plays well with it. That said, I still had to jump around to a few different places for documentation, including [this guide](https://travisdowns.github.io/blog/2020/02/05/now-with-comments.html), [this other guide](https://mademistakes.com/mastering-jekyll/static-comments/), and this [additional guide for nested replies](https://mademistakes.com/mastering-jekyll/static-comments-improved/). Along the way, to my relief, I found out that you can use openssl through the GitHub desktop app instead of having to go through the intimidating process of setting up openssl otherwise.

I tried out the version of openssl that Heroku directs you to [here](https://devcenter.heroku.com/articles/ssl-certificate-self#:~:text=If%20you%20have,Install%20with%E2%80%A6), but it's so old windows doesn't register that I'm trying to use it; so, I generated a new RSA key following the parameters laid out there anyway and tried plugging it in. 

I had some silly issues, including a failure to notice that my branch was 'main' not 'master' and I learned both about namespaces in the first place, and that the code that I'd copied skipped one (instead of site.comments.staticman.branch, all I had was site.staticman.branch - insufficient!). I was also plagued by an error regarding a favicon.ico bit, for which I am currently testing a solution in the form of updating the loading code snippet to remove redundancies.

The favicon thing is still giving me trouble, but I'm currently exploring the potential that I'm missing some step along the way for creating comments. My reference site includes a 'slug.yml' file in the data folder, so I'm going to try adding one to see if it makes things fit. As a note, I tried changing back to the original RSA key I generated and seem to be receiving no errors whatsoever Heroku-side from it, which is new (I think). 

Additional update: I think I'd originally misconfigured the github private key and RSA key portion of the setup, so I went back to verify that I had the correct private key for github and generated an entirely new RSA key for Heroku to encrypt my things-in-need-of-encryption (namely reCAPTCHA).