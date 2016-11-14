---
title: Windows Helper Tools
layout: post
thumbnail: line-chart
---

Working efficiently is all about cutting down waste of time and unnecessary thinking. That's why I want to share the tools and tweaks I use to improve my daily work as a software developer.

## Shortcuts

Know your basic shortcuts. You want to use the mouse as rarely as possible. It's not about knowing every hacky way break your fingers, it's about doing routine things faster. Look up new shortcuts that fit your needs from time to time to gradually increase your arsenal. This is by far not a complete list - it rather lists some not that popular shortcuts to give you an idea.

### Windows explorer

| Ctrl + Shift + N | New Folder |
| Ctrl + L | Jump in adress bar |
| "cmd" in explorer adress bar | Opens a cmd.exe in that directory |
| Win + 1 (2, 3, ...) | Launches the first (second, third, ...) program in the task bar |
| Win + L | Lock PC |

### Chrome

|Ctrl + L | Jump in adress bar|
|Ctrl + Shift + T | Restore last closed tab|

### Visual Studio
besides all the [R#](https://www.jetbrains.com/resharper) Shortcuts

| Alt + B then Alt + R | Rebuild all |
| Ctrl + Alt + O | Show output window |

### Other programs
(most of the times)

| Ctrl + Shift + S or F12 | Save file as | 

## Tools
### Chocolatey - package manager for windows
[Chocolatey](https://chocolatey.org/) is about the first program I install on a new windows machine. I use it to auto download, install and update the tools and programs I need. I wrote myself a little bash script that installes the most common things I use

```
cinst GoogleChrome -y
cinst dropbox -y
cinst keepass -y
cinst notepadplusplus -y
cinst 7zip -y
cinst gitextensions -y
cinst kdiff3 -y
cinst winscp -y
cinst gimp -y

choco update all -y
```

### Executor
The [Executor](http://executor.dk/) is a highly customiceable launcher for windows. It allows you to define your own commands. Some commands I use:

Start IE with new Session and URL
Start Explorer with Path
Run CMDs
Write Special Helpers

### Chrome
Chrome has one killer-feature to me and that is that you can define custom searches on 

### KeePass
Store save, generated passwords with [KeePass](http://keepass.info/) and let it auto-type your login-data whenever needed. Generate super complex passwords unique for every login and don't worry about a thing no more.

### Git
Keep all your nerd stuff version controlled in some git repository. I store my scripts and tools on [github](https://github.com/). I use [Travis CI](https://travis-ci.org/) to build and test all my stuff all the time. I even test static single page html files with tools like [html proofer](https://github.com/gjtorikian/html-proofer).

### Dropbox - or so
Use some file syncing tool to always have all your data at hand. In addition it's a great way to preserve your file for all time.