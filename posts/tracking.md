---
title: "Tracking things"
date: "2019-11-24"
template: "post"
draft: false
slug: "/posts/tracking/"
tags:
  - "habits"
  - "tools"
category: tools 
layout: layouts/post.njk
permalink: "30"
description: "Tracking tools and things to track..."
---

I'm excited to start using the [low-friction task managment system](https://github.com/CoralineAda/lftm).   I'm dreaming of combining this with [TaskWarrior.org](https://TaskWarrior.org) and the amazing open source mobile application [InThe.AM](https://inthe.am/about).

This post will hold things I've learned and things I'm trying to learn.... hopefully it will be useful to future me and perhaps future you too.

### Trying to learn
1. How to track daily habits (eating, exercise, etc).  Is good to have seven day tags, and seven contexts?
    1. `task add Exercise due:today recure:daily +habit`
    1. `task context define monday +monday or +habit` # Current context should include tasks tagged with habit
1. How to use these tools as a sort of electronic bullet journal
1. How to use these tools to do regular retrospectives 

### Learned
1. Excitement is easy because the tools seem so amazing!
1. `task add Exercise due:today recure:daily +habit`
1. `task context define monday +monday or +habit`
1. `task 34 done loaded shelfs` # Puts a note with the done
1. `task 34 show` # Shows the note with a timestamp
1. `task add Change Furnace Filter due:2020-01-25 recur:quarterly +home +habit project:chores` # no space after :

### taskwarrior backup to github
1. Top google hit is https://github.com/smaboshe/taskwarrior-backup that just makes binary tarballs of the folder.   It would be nice to be able to see the changes to the files in the commits.
1. Second google result https://github.com/kostajh/task-git looks great.  It's not synchronization and says: 
> "It is recommended to use the Taskwarrior database only on one machine, as you will be resolving conflicts if using the same task database on multiple machines."



