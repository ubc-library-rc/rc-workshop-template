#UBC Library Research Commons: workshop template

Adapted from the [just-the-docs](https://github.com/pmarsceill/just-the-docs) Jekyll template created by [Patrick Marsceil](https://github.com/pmarsceill), available as open source under the terms of the [MIT License](http://opensource.org/licenses/MIT).

## Setup

1. Create a repository for your workshop
2. Turn on _GitHub Pages_ in the new repository
  - In GitHub, go to _Settings_
  - Scroll down to the _GitHub Pages_ section
  - Under _Source_, select _master branch_

3. Create an `index.md` file. This will be the home page for your workshop site.


4. Create a `_config.yml` file in the root directory of your repository with this content:

```
title: "Name of your workshop"
remote_theme: JeremyBuhler/rc_workshop_template
search_enabled: false
aux_links:
  "UBC Library Research Commons Workshops":
    - "https://researchcommons.library.ubc.ca/workshops/"
heading_anchors: false
footer_content: "<a href=\"https://github.com/username/repository-name/\">View workshop content in GitHub</a>"
```
_Note: update `title` with your workshop title and `footer_content` with your GitHub repository URL._

## Adding content pages

Create an .md file for each page of the workshop website.  Add the following YAML header at the start of the .md file.

```
---
layout: default
title: Title of page, will appear in left navigation menu
nav_order: 1
---
```  

`nav-order` sets the order pages will appear in the navigation menu

### Adding child Pages
Each top-level page (parent) can also have sub-pages (children). The relationship between parent and child pages is defined by adding lines to the YAML header for both:

1. Add this line to the header of the parent page:

```
has_children: true
```

2. Add this line to the header of the child page:
```
parent: Title of parent page
```

## Selected configuration and formatting options

__Exclude a page from the navigation menu.__ By default the title of each .md file will appear in the left navigation menu.  To exclude a page add the following to its YAML header
```
nav_exclude: true
```

__Formatting with CSS classes.__ Use classes to apply pre-set formatting to blocks of text.  For example, use this syntax...

```  
Wash your hands frequently
{: .info}
```
... to include a note that will look like this on the published page:

Wash your hands frequently
{: .info}

### Other formatting options

__Warning__
```
Don't step on the snails!
{: .warn}
```
Don't step on the snails!
{: .warn}

__Danger__
```
Snails armed and dangerous
{: .danger}
```
Snails armed and dangerous
{: .danger}

__Prerequisites.__ To call attention to
```
- Basic slug identification
- Familiarity with slime
{: .prereq}
```
- Basic slug identification
- Familiarity with slime
{: .prereq}

__Terminal input.__ Indicates what the participant should enter in the terminal or command line.

~~~
Input
{: .label .label-green }
```
$ git status
```
~~~

Input
{: .label .label-green }
```
$ git status
```

__Terminal output.__ Shows the output that results from a an action.

~~~
Output
{: .label .label-yellow }
```
On branch master
Your branch is up-to-date with 'origin/master'.
nothing to commit, working tree clean
```
~~~

Output
{: .label .label-yellow }
```
On branch master
Your branch is up-to-date with 'origin/master'.
nothing to commit, working tree clean
```
