---
layout: default
title: Getting started
nav_order: 1
description:
---

# UBC Library Research Commons: workshop template

Adapted from the [Just the Docs](https://github.com/pmarsceill/just-the-docs) Jekyll template created by [Patrick Marsceil](https://github.com/pmarsceill) and available under the [MIT License](http://opensource.org/licenses/MIT).

Start with the instructions below to setup a Research Commons workshop repository and website. For more customization and configuration options see [Just the Docs](https://pmarsceill.github.io/just-the-docs/) documentation.

## Set up the RC workshop site

1. Create a public repository in GitHub

2. Create an `index.md` file in the root directory of the repository. This is the home page for the workshop site. Add these lines at the beginning of the `index.md` file:

```
---
layout: default
title: Title of page
nav_order: 1
---
```

3. Create a `_config.yml` file in the root directory of the repository with the content below. The *remote_theme* line points to the RC workshop template repository.

```
title: Workshop title
remote_theme: ubc-library-rc/rc-workshop-template
footer_content: "<a href=\"https://github.com/username/repository-name/\">View workshop content in GitHub</a>"
```
Update _title_ with your workshop title (will appear in top left of site) and _footer_content_ with your GitHub repository URL

In *footer_content* ensure quotation marks in the <a> tag are escaped with a `\` (see example above)
{: .warn}
  
4. In the new repository, turn on _GitHub Pages_:
  - Go to _Settings_
  - Scroll down to the _GitHub Pages_ section
  - Under _Source_, select _master branch_

After completing these steps the workshop site should be available at `https://<your_github_username>.github.io/<your_workshop_repository_name>/`
It may take a few minutes for GitHub to generate the site

## Add content pages
All workshop content is written in Markdown. Create an .md file for each page of the workshop website. Add the following YAML header at the start of each .md file.

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
- Familiarity with slime
{: .prereq}
```
...will look like this:

- Basic slug identification
- Familiarity with slime
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
