---
description: This article provides a fix for when you can't clone the Magento GitHub repository.
labels: Magento Commerce,Magento Commerce Cloud,SSH key,clone,github,how to,repository
title: Cannot clone the Magento GitHub repository
---

# Cannot clone the Magento GitHub repository

This article provides a fix for when you can't clone the Magento GitHub repository.

## Detail {#detail}

Error is similar to the following:

```terminal
Cloning into 'magento2'...
Permission denied (publickey).
fatal: The remote end hung up unexpectedly
```

## Solution {#solution}

Upload your SSH key to GitHub as discussed in [the GitHub help page](https://help.github.com/articles/generating-ssh-keys) .