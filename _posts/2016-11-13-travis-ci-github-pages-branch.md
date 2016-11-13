---
title: Travis CI and github-pages branch
layout: post
---

To my surprise travis ci does ignore the github-pages branch by default. The ranch will not be listed in travis ci and builds will not be triggered. My problem was that i had a repository with only one github-pages branch. It contained some static html content that i wanted to [html-proof](https://github.com/gjtorikian/html-proofer).


My solution was to create a "master" branch instead, change the github pages branch and the github default branch to that master and delete the old github-pages branch - no need for two branches here.

Another possible solution would be to explicitly enable the gh-pages branch in the .travis.yml file

```
branches:
   gh_pages: true
```

But i saw no extra beauty in that. I find it weird that the github-pages branch is blacklisted by default.