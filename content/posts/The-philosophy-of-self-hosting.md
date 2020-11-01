---
title: "The Philosophy of Self-Hosting"
date: 2020-11-01T00:00:00-05:00
author:
    name: Aiden Madaffri
    image: /images/avatar.png
draft: false
---

Today on the internet almost all of the applications we use on a day to day basis work via communicating with servers in the cloud. The third party could potentially be using your data for purposes other than what their application needs. Before the era of the cloud, much of this data was in our full control, we could directly manage all application data on our devices. Self-hosting allows us to regain control of our data. It is not however, the solution for everyone and has its advantages and disadvantages like all other things.


<a id="orgca92b61"></a>

## What is self-hosting?

Self-hosting is the hosting and use of applications on local hardware (referred to as a homelab) instead of relying on a third party that provides SaaS (Software as a Service). For example, instead of using a password manager that saves all your information in the cloud such as [Lastpass](https://www.lastpass.com/), you could install an instance of [Bitwarden](https://bitwarden.com/help/article/install-on-premise/) onto your own local hardware. Password managers are a prime example of the benefits of self-hosting. Now instead of having to trust that a third party is not only protecting your very personal data from hackers and from themselves, you can be 100% sure that no one gets access to your data as it lives on your own hardware.


<a id="org603f5c1"></a>

## Advantages


<a id="org8bccab3"></a>

#### Privacy

As stated above, when using products hosted by other companies or in the cloud, we throw away some of our privacy. This may vary from product to product based on their privacy policies and the objectives of those products but it still happens nevertheless. While hosting your git repositories using third parties like GitHub and GitLab may be 100% fine, other things such as our password information may be a larger concern.


<a id="org7d3f0c9"></a>

#### Automation

Not only can self-hosting accomplish most of the things we can already do with third parties, it opens up a huge new range of opportunities. This is documented more in the [Examples](#org4a5006f) section but some potential automations include network-wide ad-blocking, automatic collection of media (TV/Movie) files, personal media servers to play those files, game servers, and more.


<a id="org0163c0f"></a>

#### Education

Building a homelab does not come without difficulty, but whether you decide to run your hardware on Windows or Linux, you can learn valuable knowledge of how each operating system works and how different sections of those operating systems work together. This could be valuable information if you decide to go into an IT field or if you just want to know more about the inner working of the technologies we use on a day to day basis. My personal experience of struggling to understand and use Linux for the first time when starting my first homelab sparked a huge curiosity in the bare basics of computing. This simple experience allowed me to discover my true passion and has now started my pursuit towards a job in Information Technology.


<a id="org1bd38f6"></a>

#### Cost

This point can be somewhat debatable but in the end, I believe cost favors self-hosting. Most already have some sort of extra desktop or laptop lying around collecting dust. In instances such as these, starting a homelab is virtually free besides the cost of electricity. In cases where you don&rsquo;t already own an extra computing device, this requires an upfront payment. This is in contrast to many, though not all, third party providers that charge monthly fees to access and use their services. This monthly fee may be less expensive in the short run but over time will cumulatively become more expensive than the small upfront payment you could have put towards local hardware.


<a id="orga4211c8"></a>

## Disadvantages


<a id="org32dfcca"></a>

#### Responsibility

While privacy is a potential advantage to self-hosting, that relies on the fact that you can keep your data secure. If you leave everything on your local network without access from the public internet you are 100% safe. However, if you open up your homelab to connections over the internet, whether through a reverse proxy or other mechanisms, you open yourself up to malicious attackers. In this scenario, you are the only person who can put into place security to protect yourself. If you decide not to secure your homelab, you could be left vulnerable to attack.


<a id="org2355978"></a>

#### Time

Unlike SaaS, any software you want to set up on your homelab requires your own time and effort to set up. In some cases, it might be a one-click process, but in many others, it could be a long and tedious process to set up a new application. In addition to set up time, you also need to make sure to maintain this new software. New updates may require changes to your configurations or require new dependencies you need to install.


<a id="org4a5006f"></a>

## Examples

Below I have included some highlights of the services I host in my homelab. These could give you ideas of what you would want to do or why homelabbing may not be for you.

-   [Bitwarden](https://bitwarden.com/help/article/install-on-premise/): Self-hosted password manager that also contains my payment card information and two-factor authentication codes which can both be auto-filled on any website from any device I own.
-   [Bookstack](https://www.bookstackapp.com/): Personal Wiki where I document how I fixed problems I have encountered. It can be useful to have somewhere to look when you know you fixed the problem you are facing currently in the past but don&rsquo;t remember exactly how.
-   [code-server](https://github.com/cdr/code-server): Self-hosted instance of [Visual Studio Code](https://code.visualstudio.com/) that can be accessed from over the internet.
-   Game Servers: I have run moderately big Minecraft and Terraria servers from my homelab.
-   [GitLab-CE](https://about.gitlab.com/install/?version=ce): Self-hosted instance of GitLab where I store all my git repositories. My profile on the server can be found at <https://dev.madaffri.com/ATMTech>.
-   [Lidarr](https://lidarr.audio/)/[Sonarr](https://sonarr.tv/)/[Radarr](https://radarr.video/): Allows the automatic collection of new Music, TV Shows, or Movies respectively.
-   [Plex](https://www.plex.tv/): Essentially a personal Netflix. Allows the playing of any media files on your server from anywhere in the world.
-   [Paperless](https://github.com/the-paperless-project/paperless): Centralized manager of PDF files. This allows me to collect all my documents in one place. I also have scripts active that will automatically add documents to the server without my intervention.
-   [Pi-hole](https://pi-hole.net/): Personal DNS server that will automatically block any ads or malicious content on all devices on the network. This means even devices like iPhones will receive this ad blocking.
-   [UrBackup](https://www.urbackup.org/): Backs up all computers in my home network (multiple Windows PCs and Linux PCs) to one central location. This stores months of backups that I could restore from at any time.


<a id="orga89f4eb"></a>

## Conclusion

Is self-hosting for everyone? Certainly not, but it does open up a whole new realm of possibility in your computing experience. You are able to use and modify applications to fit your own workflow while also gaining the benefit of cutting ties with third parties and regaining control over your own data. If you do decide to embark on the journey of learning to run your own homelab, I ask that you give it a chance. It will not be easy. It will seem impossible to do what you want to do. But there&rsquo;s a point where it clicks in your head and you can do things you never would have imagined before.

