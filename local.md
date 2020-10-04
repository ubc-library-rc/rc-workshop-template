---
layout: default
title: Running locally (optional)
nav_order: 10
---
# Run a local instance of the workshop website
{: .no_toc }

<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

GitHub Pages uses Jekyll to turn markdown files into a website. This is done on GitHub's servers, so you can only see how the site will look after pushing your content to GitHub and waiting for GitHub to regenerate your site.

If you prefer to check your work locally before making it public on GitHub you'll need to run Jekyll on your own computer. Some may prefer this workflow because you can experiment and see the results of your work immediately without affecting public pages.

This page assumes you have already followed the steps in [Getting started](https://ubc-library-rc.github.io/rc-workshop-template) and have a local copy of your workshop repository (e.g. using _git clone_).

## Getting ready

To generate a local site from a workshop that uses the Research Commons template you will need to install [Ruby](https://www.ruby-lang.org/), [Jekyll](https://jekyllrb.com/) (a ruby _gem_), and several Jekyll plugins (also ruby _gems_). Familiarity with the command line will be helpful.


### Ruby

Check whether Ruby is already installed by running this command in a terminal shell.  

Input
{: .label .label-green }
```sh
ruby -v
```
If Ruby is installed the output will show the version number (Ruby v2.5 or higher is required for Jekyll).

Output
{: .label .label-yellow }
```sh
ruby 2.7.0p0 (2019-12-25 revision 647ee6f091) [x86_64-darwin19]
```
Mac OS Catalina 10.15 ships with Ruby 2.6.3 but this 'system' Ruby can cause problems related to file permissions. Install a second version of Ruby with a package manager like [RVM](https://rvm.io/rvm/install) and use that version instead.
{: .warn}

There are many ways to install Ruby. Since some may be better suited to your environment than others, this page does not provide specific step-by-step instructions. If you're not sure where to start see the [Ruby downloads page](https://www.ruby-lang.org/en/downloads/).

Once you have a suitable version of Ruby you can use it to install _gems_, open source libraries that contain Ruby code to performs certain tasks.

In Mac OS Catalina the default shell is _zsh_ instead of _bash_. Some Ruby installation guides include instructions to update _.bash_profile_. If you're using zsh, adjust accordingly.
{: .warn}

### Jekyll and Jekyll plugins

To generate a local website from a workshop using the RC template you will need to install three Ruby gems:
- jekyll
- jekyll-seo-tag
- jekyll-remote-theme

Check whether they are already installed by running `gem list`. To install any that are missing use `gem install`

```sh
gem install jekyll
```
Repeat this command for the other required gems.

If your Ruby install was successful and you're **not** using the 'system' Ruby on a Mac, this part should be painless. If you're prompted for a password or appear to need _sudo_ to make things work, something else needs fixing first. Review your Ruby setup and make sure gems are being stored in a user-accessible directory (output of the `gem env` command might help troubleshoot).

The setup above should only be required the first time.
{: .note}

## Generate your local site

In the terminal, navigate to your local copy of the workshop repository and run this command

Input
{: .label .label-green }
```sh
jekyll serve
```

Output
{: .label .label-yellow }
```sh
Configuration file: /Users/sagarana/tmp/repo-directory/_config.yml
            Source: /Users/sagarana/tmp/repo-directory
       Destination: /Users/sagarana/tmp/repo-directory/_site
 Incremental build: disabled. Enable with --incremental
      Generating...
                    done in 0.878 seconds.
 Auto-regeneration: enabled for '/Users/sagarana/tmp/repo-directory'
    Server address: http://127.0.0.1:4000/repo-directory/
  Server running... press ctrl-c to stop.
```
If your output is similar to this, congratulations! - your site is now available on _localhost_, port 4000. Open a browser and navigate to the server address shown in the output. As long as jekyll serve is running the site will update when you save changes to your local files (press _ctrl-c_ to stop serving).

Once you're satisfied with your local changes use git to push your commits to GitHub. The changes will appear on the public workshop site within a few minutes.

Jekyll creates two directories in your local repository: _.jekyll-cache/_ and *_site/*. These are only required to serve the site locally. To keep things simple, don't `git add` these directories or push them to GitHub.
{: .note}

## Wait... what about Bundler?

Many Jekyll instructions use [Bundler](https://bundler.io/) to keep track of gems and dependencies. If you're following such a guide you may come across the command `bundle exec jekyll serve` instead of `jekyll serve`.

The _bundle exec_ variant of the command **will not work** with the setup above unless you add a _Gemfile_ first. If you prefer to use Bundler, add a file named `Gemfile` to the top-level directory of your repository with this content...

```ruby
source "https://rubygems.org"

gem 'jekyll-seo-tag'
gem 'jekyll-remote-theme'
```
...then run `bundle exec jekyll serve`.

The site output should be the same but Bundler handles your gems and dependencies differently.

If you use Bundler please don't `git add` the auto-generated _Gemfile.lock_ file or push it to GitHub, as it could interfere with someone else generating the site in a different environment.
