---
layout: default
title: Update an existing workshop after a RC template update
nav_order: 3
description:
---

All of these changes need to be done manually.
Instructions updated 2025-03-31

## Required updates

This step is required; without it you will not be able to update the published website

### _config.yml 
Add another jekyll plugin. See the [updated file here](https://github.com/ubc-library-rc/template/blob/main/_config.yml)
```
 - jekyll-include-cache
```

## Optional updates

These changes are not required to update the published workshop. 

### Resources and acknowledgements
The old file was only acknowledgements but we changed it to [Resources and acknowledgements](https://github.com/ubc-library-rc/template/blob/main/resources_and_acknowledgements.md). This file can include any common links your team uses in the Resources sub-header.

### Land acknowledgement
Updated to include [multiple traditional territories](https://github.com/ubc-library-rc/template/blob/main/land-acknowledgement.md). Will include a new map with matching territories soon.

### Online (how to use Zoom)
This file was removed along with corresponding images. 

### Updated Logo
The old RC logo was replaced in the updated theme. You can find the updated image in [here](https://github.com/ubc-library-rc/rc-theme/blob/master/assets/images/rc-logo.png). Download this image and add it to the "assets/images/rc-logo.png" directory in your workshop. 
