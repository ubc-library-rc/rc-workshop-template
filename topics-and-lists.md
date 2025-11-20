---
layout: default
title: Topics and workshop lists 
nav_order: 2 
---
# Topics and workshop lists 
The Research Commons uses GitHub *topics* in a systematic way to group repositories by team and generate online lists of workshops. To assign one or more topics to your GitHub repository: 

1. go to the repository in GitHub
2. click the gear icon to the right of the list of files
3. enter topic(s) in the _Topics_ field
4. click _Save changes_


## Topics for teams
Each workshop repository should have at least one topic from the table below. Collaborative workshops may have more than on team topic.

| Topic | RC Team |
|-------|-------------|
| `citation` | Citation management |
| `data` | Data analysis and visualization |
| `digital-scholarship` | Digital Scholarship |
| `geospatial` | Geographic information systems and mapping |
| `research-data-management` | Research data management |
 
Team topics control how workshops are grouped in online lists
{: .note}


## Topics for online lists
Topics control how worskhops appear on two public-facing lists:

- <https://ubc-library-rc.github.io/all.html> for all workshops. To appear on this list a repository must have at least one team topic, in addition to the topic `workshop`.
- <https://ubc-library-rc.github.io/index.html> for featured workshops. To appear on this page the repository must _also_ have the `featured` topic. 

The lists are re-genarated nightly using a _GitHub Actions_ workflow, so changes will be visible the day after they are made.

When a repository is "archived" in GitHub settings it displays in italics on the "all workshops" list; archived workshops should not be `featured`. 
{: .note}


## _Optional:_ manual workshop lists
Teams may prefer to control their section of a workshop list manually instead of using the automatically generated list. For example: 

- The Research Data Managment team has several workshops in a single repository. To list each workshop separately they must edit manually, since the automatic process creates one list item per repository.

- Several Citation Management team workshops are not in GitHub. To include these non-repository workshops they must edit their list manually.

To change a manually edited list, edit the corresponding html file in the `ubc-library-rc.github.io` repository: 

- all workshop list: edit [manual_all_list.html](https://github.com/ubc-library-rc/ubc-library-rc.github.io/blob/master/manual_all_list.html)
- featured workshop list: edit [manual_featured_list.html](https://github.com/ubc-library-rc/ubc-library-rc.github.io/blob/master/manual_featured_list.html)

Never edit `index.html` and `all.html` files directly. These are regenerated nightly and your changes will be over-written. 
{: .warn}

Groups must choose _either_ automatic or manual workshop lists. To switch between these methods, corresponding changes must be made to `scripts/generate.js`. 
{: .note}
