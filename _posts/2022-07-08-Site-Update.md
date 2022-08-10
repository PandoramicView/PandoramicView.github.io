---
title: "Site Update!"
excerpt: "tldr; comments, my dude! AKA how I spent the first quarter of July"
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

Actually a huge pain in the ass to set up, as a person who is only moderately technical. For someone who's comfortable and familiar with the languages and structures, I imagine it wouldn't be terrible, though. I'm using [Staticman](https://staticman.net/) because I'm a fan of not requiring anyone to sign up for some kind of account, and my [jekyll](https://jekyllrb.com/) [theme](https://mmistakes.github.io/minimal-mistakes/) already plays well with it. That said, I still had to jump around to a few different places for documentation, including [this guide](https://travisdowns.github.io/blog/2020/02/05/now-with-comments.html), [this other guide](https://mademistakes.com/mastering-jekyll/static-comments/), and this [additional guide for nested replies](https://mademistakes.com/mastering-jekyll/static-comments-improved/). 

Along the way, to my relief, I found out that you can use openssl through the GitHub desktop app instead of having to go through the intimidating process of setting up openssl otherwise. I tried out the version of openssl that Heroku directs you to [here](https://devcenter.heroku.com/articles/ssl-certificate-self#:~:text=If%20you%20have,Install%20with%E2%80%A6), but it's so old windows doesn't register that I'm trying to use it; so, I just generated a new RSA key with the version that came with Git.

I had some silly issues, including a failure to notice that my branch was 'main' not 'master' and I learned both about namespaces in the first place, and that the code that I'd copied skipped one (instead of site.comments.staticman.branch, all I had was site.staticman.branch - insufficient!). I was also plagued by an error regarding a favicon.ico bit, which I think is due to the way that the site I'm referencing has their images set up - oh well, no fancy spinning load icon for now. That's some very minor UX troubleshooting for another day.

The largest hurdle for me to overcome was actually a case of good 'ol user error: I misunderstood what information I was supposed to put into the github private key field on the Heroku-side, so the app wasn't actually connecting. After many sad and fruitless attempts at properly deciphering the error messages in Chrome's inspector console, and much checking and re-checking of my site files, I figured I probably bombed outta the Heroku setup. I doubled back, verified that I had stored the correct private key (not the bit that's in the page on GitHub, but the bit that was downloaded to my PC), generated a new RSA key for Heroku to encrypt my things-in-need-of-encryption (namely reCAPTCHA), and... *voila* - comments are finally functional. 

![image-center](https://media3.giphy.com/media/KezPAZrlB01l5JN2Yg/giphy.gif?cid=790b7611004fe862a1db51b6bf6899f52b792da022cca029&rid=giphy.gif&ct=g){: .align-center}

I am straddling the feelings of 'I am awesome' and 'I am a big idiot' and that's totally cool with me.