---
title:  "Fred's ImageMagick TextEffect Utility"
date:   2019-04-21
template: "post"
draft: false
slug: "/posts/ImageMagick-TextEffect/"
tags:
  - "ImageMagick"
  - "linux"
category: linux 
layout: layouts/post.njk
permalink: "20"
description: "Easy way to make images with text."
---


Thanks, Fred!  I really like your 
[texteffect](http://www.fmwconcepts.com/imagemagick/texteffect/index.php)
utility.

1. `for f in 'Breakfast' 'Lunch' 'Dinner'; do ./texteffect -t $f  -s plain -e normal -f Arial -p 48 -c royalblue -b white -S 1024x768 $f.png; done`
2. `ls -l *.png`
```
-rwxrwxrwx 1 mpayne mpayne 39547 Apr 21 15:55 Breakfast.png
-rwxrwxrwx 1 mpayne mpayne 27169 Apr 21 15:55 Dinner.png
-rwxrwxrwx 1 mpayne mpayne 26342 Apr 21 15:55 Lunch.png
```
3. `file *.png`
```
Breakfast.png: PNG image data, 1014 x 190, 16-bit/color RGB, non-interlaced
Dinner.png:    PNG image data, 994 x 256, 16-bit/color RGB, non-interlaced
Lunch.png:     PNG image data, 985 x 277, 16-bit/color RGB, non-interlaced
```

Now to try the generated images on on the 
[Vefaii clock](https://smile.amazon.com/Calendar-Reminder-Dementia-Sufferers-Alzheimers/dp/B07J47XP34/ref=sr_1_fkmrnull_3?crid=1KY4F7LNEWODG&keywords=vefaii+dementia+clock&qid=1555879600&s=gateway&sprefix=Vefaii+clock%2Caps%2C177&sr=8-3-fkmrnull)

