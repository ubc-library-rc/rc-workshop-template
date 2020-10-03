---
layout: default
title: Running locally (optional)
nav_order: 10
description:
---
# Running the template locally (optional)

<p> GitHub Pages uses Jekyll to turn markdown files into a website. This is done on GitHub's servers, so you can only see how the site will look after pushing your content to GitHub and waiting for GitHub to regenerate your site.</p>

<p>If you prefer to check your work locally before making it public on GitHub you'll need to run Jekyll on your own computer following the directions below. This is not required but may be a preferred workflow for some content creators.</p>

These instructions assume you have already followed the steps in [Getting started](https://ubc-library-rc.github.io/rc-workshop-template) and have download a local copy of your workshop repository.

For more information about running Jekyll locally see [this page](https://docs.github.com/en/free-pro-team@latest/github/working-with-github-pages/testing-your-github-pages-site-locally-with-jekyll).
<br />

*1*{: .circle .circle-green} Install Ruby [[Mac](https://www.digitalocean.com/community/tutorials/how-to-install-ruby-and-set-up-a-local-programming-environment-on-macos)] [[Windows](https://rubyinstaller.org/)]

*2*{: .circle .circle-green} Install Jekyll [[Mac](https://jekyllrb.com/docs/installation/macos/)] [[Windows](https://jekyllrb.com/docs/installation/windows/)]

*3*{: .circle .circle-green} Open the ruby terminal
- On Windows, toggle the Windows key and search for `Start Command Prompt with Ruby`
- On Mac, open a terminal app of your preference

*4*{: .circle .circle-green} Navigate to the directory where you downloaded a local copy of your repository

    * e.g. `cd /Workspace/intro-r`

<!-- This step no longer appears to be necessary

1. Change the two following lines in `_config.yml`

    from:

    ```
    # plugins:
    #   - jekyll-seo-tag
    ```

    to

    ```
    plugins:
    - jekyll-seo-tag
    ```

    **do not commit changes in _config.yml.**

    **Make sure to revert them before pushing your changes to remote**

    -->

*5*{: .circle .circle-green} Compile & run Jekyll

    * run `gem install bundler` in the ruby terminal

    * run `bundle install` in the ruby terminal

    * run `bundle exec jekyll s` in the ruby terminal

    * It will show that jekyll is running at `http://127.0.0.1:4000/rc-workshop-template/`

    * `Ctrl + c` terminates the process

*6*{: .circle .circle-green} Edit your local copy of the repository

*7*{: .circle .circle-green} Refresh the url to check your changes  
<br/>
Once you are satisfied with your changes, push your repository back to GitHub to make them public.
