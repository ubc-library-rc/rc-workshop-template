---
layout: default
title: Getting started
nav_order: 1
description:
---

# UBC Library Research Commons: workshop template
{: .no_toc }

<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

Start with the instructions below to setup a Research Commons workshop repository and website. For more customization and configuration options see [Just the Docs](https://pmarsceill.github.io/just-the-docs/) documentation.

## Set up the RC workshop site

*1*{: .circle .circle-green} Go to <https://github.com/ubc-library-rc/template> and click the green "Use this template" button. Select "ubc-library-rc" as the owner, add a name, ensure the repository is set to "Public", then click "Create repository from template" 

*2*{: .circle .circle-green} The `_config.yml` file in your new repository contains information about the site:

```yaml
title: Title of workshop
remote_theme: ubc-library-rc/rc-theme
color_scheme: rc
github_repo_url: "https://github.com/ubc-library-rc/REPOSITORY-NAME/" 

# license information for workshop content
license_name: "Creative Commons Attribution 4.0 International License"
license_url: "http://creativecommons.org/licenses/by/4.0/"
license_image_url: "https://i.creativecommons.org/l/by/4.0/88x31.png"

plugins:
  - jekyll-remote-theme
  - jekyll-seo-tag
  - jekyll-include-cache
```

Replace the following:
- _title_ with your workshop title 
- _github_repo_url_ with your GitHub repository URL (replace only the "REPOSITORY-NAME" part)

A [Creative Commons Attribution 4.0 International License](http://creativecommons.org/licenses/by/4.0/) is applied by default. If you want to change this, update _license_name_, _license_url_ and _license_image_url_ (optional, max 150px wide), and replace the `LICENSE` file.
  {: .note}

*3*{: .circle .circle-green} In the new repository, turn on _GitHub Pages_:
- Go to _Settings_
- Scroll down to the _GitHub Pages_ section
- Under _Source_, select _Branch: main_

If you don't see these options under _GitHub Pages_ ensure the repository visibility is _public_ (see the _Change repository visibility_ setting) 
{: .note}

After completing these steps the workshop site should be available at `https://ubc-library-rc.github.io/REPOSITORY-NAME/`. It may take a few minutes for GitHub to generate the site.

*4*{: .circle .circle-green} Update the `README.md` file with your workshop title and link.

## Add/edit content pages
The template includes several files that render as pages in the workshop site:

| filename | default page title | description
| --- | --- | ---
| index.md | Outline | the workshop home page
| land-acknowledgement.md | Land acknowledgement | land acknowledgement with map from <https://native-land.ca> 
| acknowledgements.md | Acknowledgements | for copyright or content notices (default acknowledges the just-the-docs theme) 
| content/introduction.md | Introduction | placeholder for first page of lesson content

By default the `introduction.md` file is in the `content` folder, which also contains directories for images used in the site. 

Workshop content pages are written in Markdown (see [Markdown guide](https://www.markdownguide.org/basic-syntax/)). Create an .md file for each page you would like to add to the site. Include the following YAML header at the start of each .md file.

```yaml
---
layout: default
title: Title of page
nav_order: 1
---
```  
The `nav_order` line establishes where the page will appear in the navigation menu (higher numbers appear lower in the list).

### Add child pages
Top-level pages on the site (parents) can also have sub-pages (children). Child pages appear in drop-down menus below their parent. The relationship between parent and child pages is defined in the YAML headers of both pages.

Add this to the header of the parent page:

```yaml
has_children: true
```

Add this to the header of the child page:
```yaml
parent: Title of parent page
```
### TOC on parent pages
By default, all pages with children have a Table of Contents that lists the child pages after the parent page’s content. To disable, set `has_toc: false` on the parent page: 
```yaml
has_children: true
has_toc: false
```

### Exclude a page from navigation menu
By default the title of each .md file will appear in the left navigation menu.  To exclude a page add the following to its YAML header
```yaml
nav_exclude: true
```

## Selected text formatting options
Below are some formatting options that may be useful in RC worskhop sites. For more configuration options see [Just the Docs](https://pmarsceill.github.io/just-the-docs/) documentation.

### Callouts

Use this syntax...

```  
Wash your hands frequently
{: .note}
```
... to include a note that will look like this on the workshop website:

Wash your hands frequently
{: .note}


```
Don't step on the snails!
{: .warn}
```
Don't step on the snails!
{: .warn}

```
Basic slug identification; comfortable in the woods.
{: .prereq}
```

 Basic slug identification; comfortable in the woods.
{: .prereq}

### Step-by-step instructions
```
Step 1
{: .label .label-step}
Do this thing
{: .step}

Step 2
{: .label .label-step}
Do this other thing
{: .step}
```
Step 1
{: .label .label-step}
Do this thing
{: .step}

Step 2
{: .label .label-step}
Do this other thing
{: .step}


### Terminal input/output

Sometimes it's helpful to distinguish between what a workshop participant should input into the terminal or command line, and what they should expect as output. This code for an input...

~~~
Input
{: .label .label-green }
```sh
$ git status
```
~~~
... will appear like this in the workshop website:

Input
{: .label .label-green }
```sh
$ git status
```

Similarly, this code shows the output from a command:

~~~
Output
{: .label .label-yellow }
```sh
On branch master
Your branch is up-to-date with 'origin/master'.
nothing to commit, working tree clean
```
~~~

Output
{: .label .label-yellow }
```sh
On branch master
Your branch is up-to-date with 'origin/master'.
nothing to commit, working tree clean
```

### Code block syntax highlighting  
Add syntax highlighting to code blocks by specifying the language after the three backticks at the beginning of a block. The example below is for markdown (md). Other syntax options include _html, xml, js, py, sql, sh, yaml_, and many more.

~~~
```md
Code block with [markdown](https://markdownguide.org) syntax highlighting.
```
~~~

```md
Code block with [markdown](https://markdownguide.org) syntax highlighting.
```


### Circled numbers

This synax...

```
*1*{: .circle .circle-blue} Number in normal text
```
...will look like this:

*1*{: .circle .circle-blue} Number in normal text

You can also use this in headers, lists and other markdown suported elements, e.g.,

```
* *1*{: .circle .circle-blue} `.circle-blue`
* *2*{: .circle .circle-red} `.circle-red`
* *3*{: .circle .circle-yellow} `.circle-yellow`
* *4*{: .circle .circle-green} `.circle-green`
* *5*{: .circle .circle-purple} `.circle-purple`

## *2*{: .circle .circle-red} Number in h2

### *10*{: .circle .circle-yellow} Number in h3
```

...will look like this:

* *1*{: .circle .circle-blue} `.circle-blue`
* *2*{: .circle .circle-red} `.circle-red`
* *3*{: .circle .circle-yellow} `.circle-yellow`
* *4*{: .circle .circle-green} `.circle-green`
* *5*{: .circle .circle-purple} `.circle-purple`

## *2*{: .circle .circle-red} Number in h2
{: .no_toc }

### *10*{: .circle .circle-yellow} Number in h3
{: .no_toc }

### Dropdowns

To create hidden content in a dropdown use this:

~~~
<details>
<summary>This is the dropdown title</summary>
<br>
This is the hidden dropdown content.
</details>
~~~

<details>
<summary>This is the dropdown title</summary>  
<br>
This is the hidden dropdown content.
</details>  
<br />  
If you want it open by default:
~~~
<details ope
<summary>This is the dropdown title</summary>
<br>
This is the dropdown content that you can hide if you want to.
</details>
~~~

### Table of contents
See [In-page navigation with Table of Contents](https://pmarsceill.github.io/just-the-docs/docs/navigation-structure/#in-page-navigation-with-table-of-contents) for options to add a TOC within a page (like at the top of this page).
