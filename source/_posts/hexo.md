---
title: Deploy a Hexo Blog to Your GitHub Pages with a Custom Domain
tags: 'hexo, blog, github, pages'
date: 2019-04-27 02:13:26
---

## Blogging for developers

While asking around for recommendations on blogging tools, I came across [Jekyll](https://jekyllrb.com/) and [Hexo](https://hexo.io/). Both choices are popular, so it all came down to personal preference. Well, Jekyll is based on Ruby and Hexo on Node.js. It didn't take long before I decided that I would go with Hexo since I am more comfortable with JavaScript.

## Installing Hexo

Installation was a breeze because I already had the requirements installed.

### Requirements

* [Node.js](https://nodejs.org/en/)
* [Git](https://git-scm.com/)
Once you have the requirements installed, simply run the following commands on the command line:
{% codeblock %}
$ npm install -g hexo-cli
{% endcodeblock %}

## Initializing Hexo

Once Hexo is installed, run the following commands in the target `folder`:
{% codeblock %}
$ hexo init `<folder>`
$ cd `<folder>`
$ npm install
{% endcodeblock %}

## Installing Plugins

Install [`hexo-deployer-git`](https://github.com/hexojs/hexo-deployer-git) plugin:
{% codeblock %}
$ npm install hexo-deployer-git --save
{% endcodeblock %}

## Configuring Hexo

Find and open `_config.yml` to add the following adjustments:
{% codeblock %}
deploy:
  type: git
  repo: `https://username.github.io/blog`
  branch: gh-pages
  message:
{% endcodeblock %}

## Initializing Git

Initialize Git by running the following command in the command line:
{% codeblock %}
$ git init
{% endcodeblock %}

## Creating a GitHub Repository

Visit and log into [GitHub](https://github.com/) and make a new repository. Name the repository, check the `public` option, then click on `Create repository`.

## Adding a New Remote

Take the remote URL from GitHub and put it in the following command as shown below:
{% codeblock %}
$ git remote add origin `git@github.com:username/blog.git`
{% endcodeblock %}

## Generate and Deploy

Now you can deploy your sample post by running the following command:
{% codeblock %}
$ hexo -g deploy
{% endcodeblock %}

Voila!