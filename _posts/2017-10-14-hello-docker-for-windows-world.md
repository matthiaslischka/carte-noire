---
title: Hello docker-for-windows world
layout: post
---

tldnr: setting up docker-for-windows for the first time. mssql server. This is mere a personal braindump.
Easy. Probably will use docker in future to replace local mssql server and for some other things.
## Setup
Activate the `Containers` and `Hyper-V` Windows features.
![Docker Windwos Features]({{ "/assets/docker_setup_windows_features.png"}})
I use [choclatey ](https://chocolatey.org) to install all my windows programs. Therefore, installation of docker is like:
```cmd
cinst docker -y
cinst docker-for-windows -y
```
Switch from linux to windows containers.
![Switch to windows containers]({{ "/assets/docker_switch_to_windows_containers.png"}})
## Download
[Decide which image](https://hub.docker.com) you need and download it. This will take time - depending on the size of the image. Fortunately, this has to be done only once.
```cmd
docker pull microsoft/mssql-server-windows-developer
```
## Start
```cmd
docker run -d -p 1433:1433 -e sa_password=<sa_password> -e ACCEPT_EULA=Y --name sql microsoft/mssql-server-windows-developer
```
**!** The ```<sa_password>``` has to match the [mssql server password policy](https://docs.microsoft.com/en-us/sql/relational-databases/security/password-policy). Otherwise, the setup will fail and you have no idea why.
## Use
Get the container IP with this command:
{% raw %}
```cmd
docker inspect --format '{{.NetworkSettings.Networks.nat.IPAddress}}' sql
```
{% endraw %}
Now you can just connect to the mssql server using management studio, [visual studio code](https://marketplace.visualstudio.com/items?itemName=ms-mssql.mssql), ...
## Useful commands
start the sql container: `docker start sql`<br />
stop the sql container: `docker stop sql `<br />
 list running containers: `docker ps`<br />
list all containers: `docker ps -a`<br />
open a cmd.exe on the container: `cmd docker exec -it sql cmd`<br />
open sqlcmd on the container: `cmd docker exec -it sql sqlcmd`
## Conclusion
Cool first impression. Will use it much more in the future and challenge it against the real world of software development.