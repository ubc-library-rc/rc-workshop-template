---
layout: default
title: Build from scratch (superseded) 
nav_order: 2
description:
---

The recommended steps for creating a new site are at [Getting started](../index.html). Instructions on this page are kept for reference only.
{: .note}

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

*1*{: .circle .circle-green} Create a public repository in the UBC-Library-RC GitHub account.  

*2*{: .circle .circle-green} Create an `index.md` file in the root directory of the new repository. This is the home page for the workshop site. Add these lines at the beginning of the `index.md` file:

```md
---
layout: default
title: Title of page
nav_order: 1
---
## Note: this workshop is in development and not yet complete.

This is a [UBC Library Research Commons workshop](https://researchcommons.library.ubc.ca). For more information about our [upcoming workshops](https://researchcommons.library.ubc.ca/events/) and to view [our open workshop content](https://researchcommons.library.ubc.ca/oer/) find us at https://researchcommons.library.ubc.ca.
```
*3*{: .circle .circle-green} Create a `_config.yml` file in the root directory of the repository with the content below.  *remote_theme* points to the RC workshop template repository.

```yaml
title: Workshop title
remote_theme: ubc-library-rc/rc-theme
color_scheme: rc
github_repo_url: "https://github.com/ubc-library-rc/repository-name/"

# license information for workshop content
license_name: "Creative Commons Attribution 4.0 International License"
license_url: "http://creativecommons.org/licenses/by/4.0/"
license_image_url: "https://i.creativecommons.org/l/by/4.0/88x31.png"

# required for building jekyll site locally
plugins:
  - jekyll-remote-theme
  - jekyll-seo-tag
```
Update the following:
- _title_ with your workshop title (will appear in top left of site)
- _github_repo_url_ with your GitHub repository URL (link at bottom of page)
- _license_url_, _license_name_, and _license_image_url_ with the license you will apply to your content


If you're not sure what to choose, the [Creative Commons Attribution 4.0 International License](http://creativecommons.org/licenses/by/4.0/) is a good license for Research Commons OERs. The _license_image_url_ is optional (maximum 150px wide).
  {: .note}

*4*{: .circle .circle-green} In the new repository, turn on _GitHub Pages_:
- Go to _Settings_
- Scroll down to the _GitHub Pages_ section
- Under _Source_, select _Branch: main_

After completing these steps the workshop site should be available at `https://ubc-library-rc.github.io/your_workshop_repository_name/`.
It may take a few minutes for GitHub to generate the site.

*5*{: .circle .circle-green} Create a `README.MD` file with following content (at minimum)

```md
# Name of workshop
### UBC Library Research Commons

:heavy_exclamation_mark: This workshop is in development and not yet complete. :heavy_exclamation_mark:    
Link to workshop: https://ubc-library-rc.github.io/your_workshop_repository_name/

<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by/4.0/88x31.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 International License</a>.
```  
Update license information with if you choose to apply a different license to your content.

*6*{: .circle .circle-green} Create an `acknowledgments.md` file with attribution and permissions statements for material used in your workshop, as applicable. At a minimum it should have this contents

```md
---
layout: default
title: Acknowledgements
nav_order: 20
---
## Acknowledgements

Site template adapted from the [just-the-docs](https://github.com/pmarsceill/just-the-docs) Jekyll template created by [Patrick Marsceil](https://github.com/pmarsceill) and available under the [MIT License](http://opensource.org/licenses/MIT).
```
`nav-order` establishes the order pages appear in the navigation menu. Make sure `nav_order` is high enough to display the Acknowledgements link at the bottom of the menu.

## Add content pages
Workshop content pages are written in Markdown (see [Markdown guide](https://www.markdownguide.org/basic-syntax/)). Create an .md file for each page of the workshop website. Add the following YAML header at the start of each .md file.

```yaml
---
layout: default
title: Title of page, will appear in left navigation menu
nav_order: 1
---
```  

### Add child pages
Top-level pages on the site (parents) can also have sub-pages (children). Child pages appear in the navigation menu indented below their parent. The relationship between parent and child pages is defined in the YAML headers of both pages.

Add this to the header of the parent page:

```yaml
has_children: true
```

Add this to the header of the child page:
```yaml
parent: Title of parent page
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
