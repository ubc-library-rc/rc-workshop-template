---
layout: default
title: Getting started
nav_order: 1
description:
---

# UBC Library Research Commons: workshop template

Start with the instructions below to setup a Research Commons workshop repository and website. For more customization and configuration options see [Just the Docs](https://pmarsceill.github.io/just-the-docs/) documentation.

## Set up the RC workshop site

1. Create a public repository in the UBC-Library-RC GitHub account.

2. Create an `index.md` file in the root directory of the new repository. This is the home page for the workshop site. Add these lines at the beginning of the `index.md` file:

```
---
layout: default
title: Title of page
nav_order: 1
---
:heavy_exclamation_mark: This workshop is in development and not yet complete. :heavy_exclamation_mark:
```
3. Create a `_config.yml` file in the root directory of the repository with the content below.  *remote_theme* points to the RC workshop template repository.

```
title: Workshop title
remote_theme: ubc-library-rc/rc-workshop-template
footer_content: "<a href=\"https://github.com/username/repository-name/\">View in GitHub</a>"
```
    Update _title_ with your workshop title (will appear in top left of site) and _footer_content_ with your GitHub repository URL

    In *footer_content* ensure quotation marks surrounding the URL are escaped with a `\` (see example above)
    {: .warn}

4. In the new repository, turn on _GitHub Pages_:
    - Go to _Settings_
    - Scroll down to the _GitHub Pages_ section
    - Under _Source_, select _master branch_

    After completing these steps the workshop site should be available at `https://ubc-library-rc.github.io/your_workshop_repository_name/`
    It may take a few minutes for GitHub to generate the site

5. Create a `README.MD` file with following content (at minimum)

```
# Name of workshop
### UBC Library Research Commons
:heavy_exclamation_mark: This workshop is in development and not yet complete. :heavy_exclamation_mark:    
Link to workshop: https://ubc-library-rc.github.io/your_workshop_repository_name/
```  

## Add content pages
Workshop content pages are written in Markdown (see [Markdown guide](https://www.markdownguide.org/basic-syntax/)). Create an .md file for each page of the workshop website. Add the following YAML header at the start of each .md file.

```
---
layout: default
title: Title of page, will appear in left navigation menu
nav_order: 1
---
```  

`nav-order` sets the order pages will appear in the navigation menu

### Add child pages
Top-level pages on the site (parents) can also have sub-pages (children). Child pages appear in the navigation menu indented below their parent. The relationship between parent and child pages is defined in the YAML headers of both pages.

Add this to the header of the parent page:

```
has_children: true
```

Add this to the header of the child page:
```
parent: Title of parent page
```

### Exclude a page from navigation menu
By default the title of each .md file will appear in the left navigation menu.  To exclude a page add the following to its YAML header
```
nav_exclude: true
```

### (Optional) Acknowledgements page
If applicable, ackowledge content used or adapted from other sources by creating an `acknowledgements.md` file that starts with:

```
---
layout: default
title: Acknowledgements
nav_order: 10
---
```
Make sure `nav_order` is high enough to display the Acknowledgements link at the bottom of the left-hand navigation menu.

## Selected text formatting options
Below are selected formatting options that may be useful in  in RC worskhop sites.

__Notes__

Use this syntax...

```  
Wash your hands frequently
{: .note}
```
... to include a note that will look like this on the workshop website:

Wash your hands frequently
{: .note}

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

__Prerequisites.__

This synax...

```
- Basic slug identification
- Comfortable in the woods
{: .prereq}
```
...will look like this:

Something else here  
 - Basic slug identification
 - Comfortable in the woods
{: .prereq}

__Terminal input.__

Use this formatting to indicate that the participant should input text into the terminal or command line. This...

~~~
Input
{: .label .label-green }
```
$ git status
```
~~~
... will appear like this in the workshop website:

Input
{: .label .label-green }
```
$ git status
```

__Terminal output.__

Shows the output resulting from an action.  This syntax...

~~~
Output
{: .label .label-yellow }
```
On branch master
Your branch is up-to-date with 'origin/master'.
nothing to commit, working tree clean
```
~~~

...looks like this on the site:

Output
{: .label .label-yellow }
```
On branch master
Your branch is up-to-date with 'origin/master'.
nothing to commit, working tree clean
```

__Dropdowns__

To create hidden content in a dropdown use this:

~~~
<details>
<summary>This is the dropdown title</summary>
<br>
This is the hidden dropdown content.
</details>
~~~

If you want it open by default:
~~~
<details open>
<summary>This is the dropdown title</summary>
<br>
This is the dropdown content that you can hide if you want to.
</details>
~~~
