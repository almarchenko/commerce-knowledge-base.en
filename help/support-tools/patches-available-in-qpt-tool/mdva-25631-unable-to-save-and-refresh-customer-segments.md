---
description: The MDVA-25631 patch solves the issue where users are not able to save and refresh customer segments that contain a large number of customers. This patch is available when the Quality Patches Tool (QPT) 1.1.4 is installed. The patch ID is MDVA-25631. Please note that the issue was fixed in Adobe Commerce 2.4.2.
labels: QPT patches,Quality Patches Tool,Support Tools,Magento,MQP,QPT,QPT 1.1.4,on-premises,cloud infrastructure,Adobe Commerce,MDVA-25631,save,refresh,customer segments,2.3.3,2.3.2-p2,2.3.4,2.3.3-p1,2.3.5,2.3.4-p2,2.3.5-p1,2.3.5-p2
title: 'MDVA-25631: Unable to save and refresh customer segments'
---

# MDVA-25631: Unable to save and refresh customer segments

The MDVA-25631 patch solves the issue where users are not able to save and refresh customer segments that contain a large number of customers. This patch is available when the [Quality Patches Tool (QPT)](https://support.magento.com/hc/en-us/articles/360047139492) 1.1.4 is installed. The patch ID is MDVA-25631. Please note that the issue was fixed in Adobe Commerce 2.4.2.

## Affected products and versions

**The patch is created for Adobe Commerce version:**

* Adobe Commerce (all deployment methods) 2.3.3

**Compatible with Adobe Commerce versions:**

* Adobe Commerce (all deployment methods) 2.3.3 - 2.3.5-p2

>[!NOTE]
>
>The patch might become applicable to other versions with new Quality Patches Tool releases. To check if the patch is compatible with your Adobe Commerce version, update the `magento/quality-patches` package to the latest version and check the compatibility on the [QPT landing page](https://devdocs.magento.com/quality-patches/tool.html#patch-grid). Use the patch ID as a search keyword to locate the patch.

## Issue

Users are not able to save and refresh customer segments that contain a large number of customers.

<u>Prerequisites</u>:

Generate a large number of customers (more than 3 million).

<u>Steps to reproduce</u>:

1. Create a customer segment and try to save it.

<u>Expected results</u>:

The customer segment is saved without any error.

<u>Actual results</u>:

You get *500* error because the allowed memory size is being exhausted.

## Apply the patch

To apply individual patches, use the following links depending on your deployment method:

* Adobe Commerce or Magento Open Source on-premises: [Software Update Guide > Apply Patches](https://devdocs.magento.com/guides/v2.4/comp-mgr/patching/mqp.html) in our developer documentation.
* Adobe Commerce on cloud infrastructure: [Upgrades and Patches > Apply Patches](https://devdocs.magento.com/cloud/project/project-patch.html) in our developer documentation.

## Related reading

To learn more about Quality Patches Tool, refer to:

* [Quality Patches Tool released: a new tool to self-serve quality patches](https://support.magento.com/hc/en-us/articles/360047139492) in our support knowledge base.
* [Check if patch is available for your Adobe Commerce issue using Quality Patches Tool](https://support.magento.com/hc/en-us/articles/360047125252) in our support knowledge base.

For info about other patches available in QPT, refer to the [Patches available in QPT](https://support.magento.com/hc/en-us/sections/360010506631-Patches-available-in-MQP-tool-) section.