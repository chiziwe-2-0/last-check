## Tor Onion Service On Heroku
![image](https://img.shields.io/badge/Heroku-430098?style=for-the-badge&logo=heroku&logoColor=white) ![image](https://img.shields.io/badge/Tor-7D4698?style=for-the-badge&logo=Tor-Browser&logoColor=white)

[![FOSSA Status](https://app.fossa.com/api/projects/git%2Bgithub.com%2Fsumithemmadi%2FTor-Onion-Service-On-Heroku.svg?type=shield)](https://app.fossa.com/projects/git%2Bgithub.com%2Fsumithemmadi%2FTor-Onion-Service-On-Heroku?ref=badge_shield)
[![Version](https://img.shields.io/badge/Version-1.0.3-blue)](https://github.com/sumithemmadi/Tor-Onion-Service-On-Heroku)
[![Licence](https://img.shields.io/github/license/sumithemmadi/Tor-Onion-Service-On-Heroku)](https://github.com/sumithemmadi/Tor-Onion-Service-On-Heroku)
[![issues](https://img.shields.io/github/issues/sumithemmadi/Tor-Onion-Service-On-Heroku)](https://github.com/sumithemmadi/Tor-Onion-Service-On-Heroku)
[![stars](https://img.shields.io/github/stars/sumithemmadi/Tor-Onion-Service-On-Heroku)](https://github.com/sumithemmadi/Tor-Onion-Service-On-Heroku)

Host Tor v3 Hidden Service in dark web using heroku

Try my another repository built with php   https://github.com/sumithemmadi/tor-hidden-service-on-heroku/



## Manually Deploy to Heroku

### Prerequisites

![image](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white) ![image](https://img.shields.io/badge/PHP-777BB4?style=for-the-badge&logo=php&logoColor=white) ![image](https://img.shields.io/badge/git-000000?style=for-the-badge&logo=git&logoColor=white) ![image](https://img.shields.io/badge/Tor-7D4698?style=for-the-badge&logo=Tor-Browser&logoColor=white) 
- 1 . `nodejs`
- 2 . `tor` - v3
- 3 . `php`
- 4 . `git`
- 5 . `Heroku CLI`

### Install Heroku
![image](https://img.shields.io/badge/Heroku-430098?style=for-the-badge&logo=heroku&logoColor=white)

- 1 . Create an account on  **[https://heroku.com](https://heroku.com)**.
- 2 . Install the Heroku CLI on your computer: <br/>**[https://devcenter.heroku.com/articles/heroku-cli](https://devcenter.heroku.com/articles/heroku-cli)**. 
<br/>Check that you have the `heroku-cli` installed by checking the version number in your terminal:
```bash
heroku --version
```
- 3 . Connect the `Heroku CLI` to your account by writing the following command in your terminal and follow the instructions on the command line.
```bash
heroku login
```


### Quick Start

- 1 . Create a new project, for example in my case  `Project` and go to that directory.

- 2 . Clone this repository with below command
```bash
git clone https://github.com/chiziwe-2-0/Tor-Onion-Service-On-Heroku.git
cd Tor-Onion-Service-On-Heroku
```
- 3 . Create a heroku application
```bash
heroku apps:create App-Name
```
-  `heroku apps:create App-Name` this command creates the application as well as a git remote, that you can use to push your code to Heroku.

    > _Note: replace `App-Name` with  any other name._
```bash
 $ heroku apps:create tor-onion
 Creating ⬢ tor-onion... done
 https://tor-onion.herokuapp.com/ | https://git.heroku.com/tor-onion.git
```
- 4 . Now add three buildpacks `heroku/nodejs` ,`heroku/php` and `heroku-community/apt` to you application.


- - heroku/nodejs

```bash
heroku buildpacks:set heroku/nodejs
```

- - heroku-community/apt

```bash
heroku buildpacks:add --index 1 heroku-community/apt
```

- - heroku/php

```bash
heroku buildpacks:set heroku/php
```

- Sometimes adding 2nd buildpack will remove 1st one (or) adding 3rd buildpack will remove 2nd one ,try adding all three buildpacks again and again one by one untill you see three buildpacks added as shown in below picture.

![image](https://raw.githubusercontent.com/sumithemmadi/Tor-Onion-Service-On-Heroku/gh-pages/images/builtpack.jpg)
- 6 . Copy your website file's to the folder `site` <br>
      eg :- index.html,index.php [default=index.html]

- 7 . Copy the following files to `temp/var/lib/tor/hidden_service` dir<br> 

   - `hostname`
   - `hs_ed25519_public_key`
   - `hs_ed25519_secret_key`


    > If you don't know where these files stored refer to **[https://2019.www.torproject.org/docs/tor-onion-service](https://2019.www.torproject.org/docs/tor-onion-service)**
  

- 8 . Deploy your changes to heroku
```bash
git add .
git commit -am "Updated"
git push heroku
```

- _Now your app is accessible over Tor_
## To know your .onion address
- Run below command to know your onion address.

```bash
heroku run cat temp/var/lib/tor/hidden_service/hostname
```
![Image](https://raw.githubusercontent.com/sumithemmadi/Tor-Onion-Service-On-Heroku/gh-pages/images/hostname.jpg)
## Get onion link on heroku app
-  If you still can't find your .onion link. <br> Open your heroku app <br>`https://App-Name.herokuapp.com` and click on `show my .onion link`.
   > _Note : Due to herokus policies, a single web dyno is sent to sleep after 30 minutes of inactivity. This means if your application has not served any requests for 30 minutes, it is forced to sleep by heroku and has to wake up prior to serve a new request, which easily can take up to 30–40 seconds. Generally free dynos will sleep (shut down) after 30 minutes of inactivity. This is actually a feature to avoid using up your free dyno hours. To prevent Heroku app from idling add [New Relic add-on](https://elements.heroku.com/addons/newrelic). It has an availability monitor feature that will ping your site twice per minute, thus preventing the dyno from idling (Or) add  [Uptimerobot](https://uptimerobot.com/) it is free and offers 5 min interval site checking._

-  Here is my app 
    **[https://tor-onion.herokuapp.com/](https://tor-onion.herokuapp.com/)**


## License
[![FOSSA Status](https://app.fossa.com/api/projects/git%2Bgithub.com%2Fsumithemmadi%2FTor-Onion-Service-On-Heroku.svg?type=large)](https://app.fossa.com/projects/git%2Bgithub.com%2Fsumithemmadi%2FTor-Onion-Service-On-Heroku?ref=badge_large)
