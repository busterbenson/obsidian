---
title: Installation Instructions
date: 2020-07-09
---

### Install things
- Install [Obsidian](https://obsidian.md/). 
- Install `lettersmith_py` from [here](https://github.com/gordonbrander/lettersmith_py).
- Download [kev_mcg's starter repo](https://github.com/kmcgillivray/obsidian-lettersmith) to your computer. 

### Create the new site & repo
- Run `cd obsidian-lettersmith`
- Run `python3 build.py` to build the site.
- Run `pip freeze > requirements.txt` to create a file that let's Netlify know where to find `letterpress_py`.
- Run `echo 3.7 > runtime.txt` to let Netlify know to use a modern enough Python version to support lettersmith.
- Create a new repo on [Github](https://github.com).
- Run `git remote add origin https://github.com/user/[your repo name].git` to link your new site to the new Github repo.
- Go to [Netlify](https://netlify.com) and create an account, then connect [your repo name] Github repo to it.
- Click on your new Netlify site, then click on "Deploys" and "Deploy Settings". Edit the build settings to set the "Build Command" to `python3 build.py` and the "Publish Directory" to `public`.
- Try deploying. It might give you a "mixed content" warning about how some of your content is linking to another site.
- Edit `build.py` with a text editor to update `base_url` to match the URL you have in Netlify. 
- `git commit -am "update base_url to match netlify"`
- `git push origin master`
- Wait for your site to automatically deploy, then the Base URL you just specified. Hopefully it'll work!
