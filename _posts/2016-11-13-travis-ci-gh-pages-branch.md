---
title: Travis CI and gh-pages branch
layout: post
---

To my surprise travis ci does ignore the gh-pages branch by default. The branch will not be listed in travis ci and builds will not be triggered. My problem was that i had a repository with only one gh-pages branch. It contained some static html content that i wanted to [html-proof](https://github.com/gjtorikian/html-proofer).

My solution was to create a "master" branch instead, change the github pages branch and the github default branch to that master and delete the old gh-pages branch - no need for two branches here.

Another possible solution would be to explicitly enable the gh-pages branch in the .travis.yml file
```
branches:
   gh-pages: true
```
But i saw no extra beauty in that. Imho it is weird that the gh-pages branch is blacklisted by default.