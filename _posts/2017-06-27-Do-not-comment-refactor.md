---
title: Do not comment. Refactor.
layout: post
---

Easy as that. Almost always comments are just an indicator that your code is still not readable enough.
```
//'home' is the default tab
this.activeTab = 'home';
```
...could be refactored to something like...
```
activeTab = constants.defaultTab;
```
From time to time comments also try to be something that they should not try to be in the first place: like a story in the backlog, an issue in your tracking system or a clarification task for the product owner…

``//clarify how this should be done when customer xzy ....``
*(we can't clarify here. this is dev country)*

And then, of course, there will always be the *refactoring-leftover* comment aka “I don’t want to delete that quite yet” or the *repeat-the-method-name* comment aka "``/*does that*/ public void doesThat()``" or the *I’m-funny* comment aka "``//magic happens here``"...

![useless comment]({{"/assets/comments_wet_floor.jpg"}})

You geht the point. Get rid of those right way and refactor away all the rest...