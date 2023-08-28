+++ 
draft = false
date = 2023-08-27T22:22:13+05:30
title = "How did I made the website"
description = ""
slug = ""
authors = []
tags = []
categories = []
externalLink = ""
series = []
+++

### 1) Install Hugo

**sudo pacman -S hugo** 

### 2) Create two repo named <username>.github.io and blog

### 3) Clone these two repositories, make a README.md in <username>.github.io and make an initial commit and push.

### 4) Create a hugo site in blog repo. Download the theme you want from hugo themes website and move it to themes directory of the hugo site. 

### 5) In hugo.toml, change baseURL to 'https://<username>.guthub.io/', give appropriate title and add "theme = '<The theme you wanted>'.

### 6) In themes/<The theme>, edit the config.toml and add the example config from the theme creator and edit accordingly. You can add an image, name, whatever you want.

### 7) To preview the website, start a local server from the root of the site directory. The -w watches filesystem for changes and recreate as needed. And -D make drafts visible. Then when you open the link provided, you can see your website and edit accordingly

**hugo server -w -D** 

### 8) To make posts, add layout of the post in archetypes directory as posts.md and make post using this command:

**hugo new posts/<post_name>.md**

### In hugo site directory, create a submodule of main branch of <username>.github.io to a new directory called public.

**git submodule add -b main <github_repo_link> public**

### To build your site
**hugo -t <theme>**

### Push everything to github from blog github clone

git add . && git commit -m 'commit' -a && git push

### This will make the website active