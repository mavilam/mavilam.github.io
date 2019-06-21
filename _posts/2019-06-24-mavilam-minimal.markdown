---
layout: post
title:  "mavilam-minimal Jekyll theme"
date:   2019-06-24 22:43:48 +0100
categories: bot
---

Two years ago, more or less, I published the first version of my site. I choose Jekyll since I was a static site, and I installed the awesome [Swiss by broccolini](https://github.com/broccolini/swiss) theme.

When I began to write the newsletter, the site needed a tiny reformat, so I change Swiss to adapt it to my new idea. It was possible because Swiss is open source so that I could change the layouts to my desires.

Since these changes were made, I realize that I would want to make the site design more personal. To use an out of the box theme or one with some tweaks was not enough. That was the begin of the idea about [mavilam-minimal](https://github.com/mavilam/mavilam-minimal) ✨✨, my own open source Jekyll theme.

Actually it was a challenge for me because I don't know Ruby and design is not one of my capabilities. After all the process, I could say that i pass through three stages in the development of the theme:

* **Creation**: Like everyone in the beginning of a project, I was lost. In order to create the boiler-plate and upload the Gem (I don't have much Ruby knowledge) I found [this tutorial](https://medium.com/@jameshamann/creating-your-own-jekyll-theme-gem-1f8180a0e4b8) by [James Hamann](https://twitter.com/jameshamann) that is pretty complete.

* **Design/Development**: This is the main stage of the project. The theme is composed just by liquid, HTML and CSS. CSS for me is magic. My idea is pretty simple and minimalistic, so after surfing other personal blog and collect ideas I drew a mock with the ideas that I wanted to develop. When the idea was barely complete, I tried to develop one by one the features of the blog with the research of CSS and liquid associated due to my lack of knowledge in these fields. One of the most useful resources was [this web](https://coolors.co/e4fde1-3f5d3e-5cd199-c1c1c5-ffbf46) that I used to choose the correct colors. My favorite part of the theme is that if your computer or phone is in dark/light mode the web adapts its color to the mode 🤩🤩.

* **Deployment**: In first place I thought that GitHub pages was compatible with all kind of Jekyll themes *(spoiler: I was wrong)* but when I upload the site with the new theme it was displayed in plain text. GitHub does not give you the real log of the deployment, they sent an email with a description of the error. To check the failure and fix it I created a TravisCI pipeline. After several iterations I realized that GitHub pages only support [these themes](https://pages.github.com/themes/) so it is needed to put the layouts and assets of the theme in your site instead of just indicate the theme name in the _config.yml.


To sum up, to build something from zero with almost no knowledge of the technology involved was so refreshing and interesting. I know that there are so many things to be improved (Pull Requests are welcome) but I'm pretty proud that the theme that I'm is developed entirely by.
