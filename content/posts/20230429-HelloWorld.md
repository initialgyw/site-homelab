---
author: konri
date: 2023-04-29
next: /posts/20230430-terraformcloud
linktitle: Hello World!
title: Hello World!
---

In order to understand how new technologies work, I need a hands-on practice environment to implement the latest technological changes. My homelab will be the pillar of my knowledge acquisitions. Maybe this site can be my career portfolio?

I've been writing a lot more as I climb up the corporate ladder: writing proof of concepts, documentations, policies, and performance reviews. Using this platform will hopefully improve my writing skills and enhance my ability to organize my thoughts on "paper".

<!--more-->

## Homelab Philosophy

The idea for my homelab will be an hybrid on-premise and cloud environment. I will try to utilize free/affordable cloud services and incorporate it into my homelab.

## Existing Services

I already have some existing services that I need to note.

- **Github for code respository**

  Github provides a free service to store my code publicly and privately. It was a hard choice between Github and GitLab but I'm sticking with Github due to popularity and maybe integration with Azure (if any) for future projects.

  There is also a command line tool for GitHub and can be installed via:

  {{< tabs "2023042901" >}}
  {{< tab "MacOS" >}}
  
  ```zsh
  brew install gh

  konri@macmini-m2 ~ % gh auth login       
  ? What account do you want to log into? GitHub.com
  ? What is your preferred protocol for Git operations? HTTPS
  ? Authenticate Git with your GitHub credentials? Yes
  ? How would you like to authenticate GitHub CLI? Login with a web browser

  ! First copy your one-time code: H2G4-23K4
  Press Enter to open github.com in your browser... 
  ✓ Authentication complete.
  - gh config set -h github.com git_protocol https
  ✓ Configured git protocol
  ✓ Logged in as initialgyw
  ```

  {{< /tab >}}
  {{< /tabs >}}

  This tool allows me to interact with GitHub without the web browser. That is always a plus as I am a command line kinda guy.

- **Cloudflare for DNS**

  I bought my domain using [porkbun.com](https://porkbun.com) registrar but decided to use Cloudflare's DNS service due to a lot of application support (Terraform, Ansible, etc). Cloudflare also provides email routing and web page caching, which I do not get with my domain registrar. I looked into [NS1](https://ns1.com) which has geographic filtering, but I'm going to stick with Cloudflare for now. I'll write a blog if I ever migrate to use NS1.

  I will also be using [Cloudflare Pages](https://pages.cloudflare.com/) to deploy this site from [site-homelab.ricebucket.dev GitHub repository](https://github.com/initialgyw/site-homelab.ricebucket.dev).

- **Lucidcharts**

  This SaaS will be used for editing my homelab topologies. Are there any other free tools available for me to record my topologies?

## Why Cloudflare Pages with Hugo

A fresh start on my homelab means I don't have any servers to host contents, as these servers are not yet configured. [Cloudflare Pages](https://pages.cloudflare.com/) does not require me to run any servers or database backend and thinking about the future, maybe it's time to start embracing Platform-as-a-Service, everywhere.

Cloudflare Pages aligns with my homelab philosophy; *utilize free/affordable cloud services*. It has a lot of free features, such as caching and DDoS protection for site hosting. This website consists of static pages so I don't need to worry about security as much. I also don't need to worry about site performance or network bandwidth usage. Cloudflare should also be able to handle my puny traffic. I am also heavily vested in NET, so it would be a good idea to understand the products of Cloudflare.

*Since the contents will be stored on a Github repository, why not use [Github Pages](https://pages.github.com/) to centralize the location of storage and deployment?* Github Pages does not have traffic analytics. I need to add in a third-party code to get traffic data, such as Google Analytics. Cloudflare has built-in analytics through their proxies so embracing that would make my site more miminalistic.

I picked Hugo (over other static site generators, Jekyll, Pelican) due to popularity (more community support). Cloudlfare allows me to Continuously Develop and Continuously Integrate to automatically generate static pages and push it publicly just by committing the changes to the Github repository.
