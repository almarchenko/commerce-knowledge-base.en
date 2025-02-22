---
description: The MDVA-37364 patch solves the issue where the custom customer attribute of date type breaks the Customer Grid UI. This patch is available when the Quality Patches Tool (QPT) 1.1.2 is installed. The patch ID is MDVA-37364. Please note that the issue is scheduled to be fixed in Adobe Commerce version 2.4.4.
labels: QPT patches,Quality Patches Tool,QPT,MQP,Support Tools,QPT 1.1.2,Magento,Adobe Commerce,on-premises,cloud infrastructure,customer attribute,custom,grid UI,broken,2.4.0,2.4.0-p1,2.4.1,2.4.1-p1,2.4.2,2.4.2-p1,2.4.2-p2
title: 'MDVA-37364: Custom customer attribute of date type breaks Grid UI'
---

# MDVA-37364: Custom customer attribute of date type breaks Grid UI

The MDVA-37364 patch solves the issue where the custom customer attribute of date type breaks the Customer Grid UI. This patch is available when the [Quality Patches Tool (QPT)](https://support.magento.com/hc/en-us/articles/360047139492) 1.1.2 is installed. The patch ID is MDVA-37364. Please note that the issue is scheduled to be fixed in Adobe Commerce version 2.4.4.

## Affected products and versions

**The patch is created for Adobe Commerce version:**

* Adobe Commerce (all deployment methods) 2.4.2

**Compatible with Adobe Commerce versions:**

* Adobe Commerce (all deployment methods) 2.4.0-2.4.2-p2

>[!NOTE]
>
>The patch might become applicable to other versions with new Quality Patches Tool releases. To check if the patch is compatible with your Adobe Commerce version, update the `magento/quality-patches` package to the latest version and check the compatibility on the [QPT landing page](https://devdocs.magento.com/quality-patches/tool.html#patch-grid). Use the patch ID as a search keyword to locate the patch.

## Issue

Custom customer attribute of date type breaks the Customer Grid UI.

<u>Steps to reproduce</u>:

1. Create a custom attribute with date type:
    * Go to **Stores** > **Attributes** > **Add Attribute**.
    * Set the Input Type to Date.
    * Set the Add to Column Options to Yes.
    * Save the attribute.
1. Go to **Admin** > **Customers** > **All Customers**.
    * Add the newly added custom attribute to the grid from the columns option.
1. Create/Edit a customer and set the value of the created custom date attribute field.
1. Save, reindex, and clear cache.
1. Go to **Customers** > **All Customers**.
    * Check the Customer Grid.

<u>Expected results</u>:

The Admin Customer Grid shows all data including the new date custom attribute without breaking the Customer Grid UI.

<u>Actual results</u>:

The Admin Customer Grid UI is broken.

## Apply the patch

To apply individual patches, use the following links depending on your deployment type:

* Adobe Commerce or Magento Open Source on-premises: [Software Update Guide > Apply Patches](https://devdocs.magento.com/guides/v2.4/comp-mgr/patching/mqp.html) in our developer documentation.
* Adobe Commerce on cloud infrastructure: [Upgrades and Patches > Apply Patches](https://devdocs.magento.com/cloud/project/project-patch.html) in our developer documentation.

## Related reading

To learn more about Quality Patches Tool, refer to:

* [Quality Patches Tool released: a new tool to self-serve quality patches](https://support.magento.com/hc/en-us/articles/360047139492).
* [Check if patch is available for your Adobe Commerce issue using Quality Patches Tool](https://support.magento.com/hc/en-us/articles/360047125252).

For info about other patches available in QPT, refer to the [Patches available in QPT](https://support.magento.com/hc/en-us/sections/360010506631-Patches-available-in-MQP-tool-) section.