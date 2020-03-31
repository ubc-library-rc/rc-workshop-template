---
layout: default
title: Running locally (GAAs only)
nav_order: 10
description:
---



# Running the template locally

1. Install Ruby [[Mac](https://www.digitalocean.com/community/tutorials/how-to-install-ruby-and-set-up-a-local-programming-environment-on-macos)] [[Windows](https://rubyinstaller.org/)]

1. Install Jekyll [[Mac](https://jekyllrb.com/docs/installation/macos/)] [[Windows](https://jekyllrb.com/docs/installation/windows/)]

1. Open the ruby terminal

    * On Windows, toggle the Windows key and search for `Start Command Prompt with Ruby`

    * On Mac, open a terminal app of your preference

1. Navigate to the directory where you downloaded this repo

    * e.g. `cd /Workspace/intro-r`

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

6. Compile & run Jekyll

    * run `gem install bundler` in the ruby terminal
    
    * run `bundle install` in the ruby terminal

    * run `bundle exec jekyll s` in the ruby terminal

    * It will show that jekyll is running at `http://127.0.0.1:4000/rc-workshop-template/`

    * `Ctrl + c` terminates the process

1. Edit Markdown files 

1. Refresh the url and check changes. 

1. Delete `local.md` in any workshop cloned from the template


