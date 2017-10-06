---
title: Hello docker-world
layout: post
---
tldnr: setting up docker for windows for the first time. This is mere a personal braindump.
Easy. Probably will use docker in future to replace local mssql server and for some other things.
## setup
To setup windows activate the ```Containers``` and ```Hyper-V``` Windwos Feature.
<<WINDOWS FEATURE IMAGE>>
I use [choclatey ](https://chocolatey.org) to install all my windows programs. Therefore, installation of docker is like:
```
cinst docker -y
cinst docker-for-windows -y
```
## download
Decide which image you need and download it. This will take time - depending on the size of the image. In this case 4GB. Fortunately, this has to be done only once.
```
docker pull microsoft/mssql-server-windows
```
## start
```
docker run -d -p 1433:1433 -e sa_password=<sa_password> -e ACCEPT_EULA=Y --name sql microsoft/mssql-server-windows
```
**!** The ```<sa_password>``` has to match the [mssql server password policy](https://docs.microsoft.com/en-us/sql/relational-databases/security/password-policy). Otherwise, the setup will fail and you have no idea why.
## use
Easiest way to use it is by IP. Get the container IP with this command:
```
docker inspect --format '{{.NetworkSettings.Networks.nat.IPAddress}}' sql
```
And just in case you need to open a ```cmd.exe``` on the container:
```
docker exec -it sql cmd
```
## conclusion
Cool first impression. However, I am in no position to recommend or not recommend it as of yet.
Will use it much more in the future and challenge it against the real world of software development.