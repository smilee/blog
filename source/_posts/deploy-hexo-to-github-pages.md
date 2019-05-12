---
title: Deploy a Hexo Blog to Your GitHub Pages
categories:
- blog
- hexo
tags: 
- hexo
- blog
- github
- github pages
- development
keywords:
- blog
date: 2019-04-27 02:13:26
metaAlignment: center
coverImage: https://images.unsplash.com/photo-1517148815978-75f6acaaf32c?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1950&q=80
coverMeta: out
coverSize: partial
---

While asking around for recommendations on blogging tools, I came across [Jekyll](https://jekyllrb.com/) and [Hexo](https://hexo.io/). Both choices are popular, so it all came down to personal preference. <!-- more -->Well, Jekyll is based on Ruby and Hexo on Node.js. It didn't take long before I decided that I would go with Hexo since I am more comfortable with JavaScript.

## Installing Hexo

Installation was a breeze because I already had the requirements installed.

### Requirements

* [Node.js](https://nodejs.org/en/)
* [Git](https://git-scm.com/)

Once you have the requirements installed, simply run the following command on the command line to install Hexo:

``` bash
$ npm install -g hexo-cli
```

## Initializing Hexo

Once Hexo is installed, run the following commands in the target `folder`:

``` bash
$ hexo init <folder>
$ cd <folder>
$ npm install
```

## Installing Plugins

Install [`hexo-deployer-git`](https://github.com/hexojs/hexo-deployer-git) plugin:

``` bash
$ npm install hexo-deployer-git --save
```

## Configuring Hexo

Find and open `_config.yml` to add the following adjustments:

``` yml
deploy:
  type: git
  repo: https://username.github.io/blog
  branch: gh-pages
  message:
```

## Initializing Git

Initialize Git by running the following command in the command line:

``` bash
$ git init
```

## Creating a GitHub Repository

Visit and log into [GitHub](https://github.com/) and make a new repository. Name the repository, check the `public` option, then click on `Create repository`.

## Adding a New Remote

Take the remote URL from GitHub and put it in the following command as shown below:

``` bash
$ git remote add origin git@github.com:username/blog.git
```

## Generate and Deploy

Now you can deploy your sample post by running the following commands:

``` bash
$ hexo generate
$ hexo deploy
```

Voila!