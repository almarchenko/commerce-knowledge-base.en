---
description: The MDVA-40545 patch solves the issue where only the first node for a page is retrieved even if there are more than one node for the same page. This patch is available when the Quality Patches Tool (QPT) 1.1.5 is installed. The patch ID is MDVA-40545. Please note that the issue is scheduled to be fixed in Adobe Commerce 2.4.4.
labels: QPT patches,Quality Patches Tool,MQP,QPT,Adobe Commerce,Magento,cloud infrastructure,on-premises,Support Tools,node,retrieve,filter,sub-menu,breadcrums,2.3.0,2.3.1,2.3.2,2.3.3,2.3.2-p2,2.3.4,2.3.3-p1,2.3.5,2.3.4-p2,2.3.5-p1,2.3.5-p2,2.3.6,2.3.6-p1,2.3.7,2.3.7-p1,2.3.7p2,2.4.0,2.4.0-p1,2.4.1,2.4.1-p1,2.4.2,2.4.2-p1,2.4.2-p2,2.4.3,2.4.3-p1
title: 'MDVA-40545: Only the first node for a page is retrieved'
---

# MDVA-40545: Only the first node for a page is retrieved

The MDVA-40545 patch solves the issue where only the first node for a page is retrieved even if there are more than one node for the same page. This patch is available when the [Quality Patches Tool (QPT)](https://support.magento.com/hc/en-us/articles/360047139492) 1.1.5 is installed. The patch ID is MDVA-40545. Please note that the issue is scheduled to be fixed in Adobe Commerce 2.4.4.

## Affected products and versions

**The patch is created for Adobe Commerce version:**

* Adobe Commerce (all deployment methods) 2.4.2

**Compatible with Adobe Commerce versions:**

* Adobe Commerce (all deployment methods) 2.3.0 - 2.4.3-p1

>[!NOTE]
>
>The patch might become applicable to other versions with new Quality Patches Tool releases. To check if the patch is compatible with your Adobe Commerce version, update the `magento/quality-patches` package to the latest version and check the compatibility on the [QPT landing page](https://devdocs.magento.com/quality-patches/tool.html#patch-grid). Use the patch ID as a search keyword to locate the patch.

## Issue

Only the first node for a page is retrieved even if there are more than one node for the same page.

<u>Steps to reproduce</u>:

1. In the Admin Panel, go to **Hierarchy** and add two menu items/nodes.
1. Add the same CMS page to each node.
1. Clear cache and check the frontend.
1. Check link and breadcrumbs for the first added sub-menu.
1. Check link and breadcrumbs for the second added sub-menu.

<u>Expected results</u>:

Breadcrumbs and link on the second sub-menu are relevant to the second node.

<u>Actual results</u>:

Breadcrumbs and link on the second sub-menu are the same as the first sub-menu.

## Apply the patch

To apply individual patches, use the following links depending on your deployment method:

* Adobe Commerce or Magento Open Source on-premises: [Software Update Guide > Apply Patches](https://devdocs.magento.com/guides/v2.4/comp-mgr/patching/mqp.html) in our developer documentation.
* Adobe Commerce on cloud infrastructure: [Upgrades and Patches > Apply Patches](https://devdocs.magento.com/cloud/project/project-patch.html) in our developer documentation.

## Related reading

To learn more about Quality Patches Tool, refer to:

* [Quality Patches Tool released: a new tool to self-serve quality patches](https://support.magento.com/hc/en-us/articles/360047139492) in our support knowledge base.
* [Check if patch is available for your Adobe Commerce issue using Quality Patches Tool](https://support.magento.com/hc/en-us/articles/360047125252) in our support knowledge base.

For info about other patches available in QPT, refer to the [Patches available in QPT](https://support.magento.com/hc/en-us/sections/360010506631-Patches-available-in-MQP-tool-) section.