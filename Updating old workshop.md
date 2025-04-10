---
layout: default
title: Update existing workshop after a template update
nav_order: 3
description:
---

The Research Commons occasionally updates the [rc-theme]() and [template]() repositories that govern the layout and default content of workshop websites. After an update:

1. Theme-related changes are automatically applied the next time the workshop is updated (e.g. changes to layout, colour, footers, etc.)
2. Template-related changes may be applied manually, if desired (e.g. changes to default pages or content)

## Update steps
The most recent theme and template updates happened in __March 2025__.

### Required
Each workshop repository has a `_config.yml` file with metadata and configuration information. After the March 2025 template upgrade, this file must include a reference to the `jekyll-include-cache` plugin, otherwise website updates will fail. The last four lines of your file should look like this:

```
plugins:
  - jekyll-remote-theme
  - jekyll-seo-tag
  - jekyll-include-cache
```

In most repositories you will only need to add the last line, but some older repositories might be missing the entire `plugins:` section (see [sample `_config.yml` file](https://github.com/ubc-library-rc/template/blob/main/_config.yml)).

### Optional
These changes are not required but teams might choose to apply them for consistency. 

| File | Change |
| --- | --- |
| [Resources_and_acknowledgements.md](https://github.com/ubc-library-rc/template/blob/main/resources_and_acknowledgements.md) | Replaces the previous "acknowledgements" file; includes a "Resources" sub-header for RC links and other relevant content  |
| [land-acknowledgement.md](https://github.com/ubc-library-rc/template/blob/main/land-acknowledgement.md) | __In development:__ will be modified to include a <https://native-land.ca> map showing Musqueam, Squamish, and Tsleil-waututh territories |
| online.md | This file was removed along with corresponding images (contained instructions for interacting on Zoom that are no longer considered necessary) |
