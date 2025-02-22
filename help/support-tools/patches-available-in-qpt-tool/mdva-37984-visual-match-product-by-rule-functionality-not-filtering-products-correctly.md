---
description: "The MDVA-37984 patch solves the issue where the Visual Merchandiser's \u201CMatch product by rule\u201D functionality does not filter products correctly when staging updates are applied. This patch is available when the Quality Patches Tool (QPT) 1.1.9 is installed. The patch ID is MDVA-37984. Please note that the issue is scheduled to be fixed in Adobe Commerce 2.4.5."
labels: QPT patches,Quality Patches Tool,Support Tools,Magento,Adobe Commerce,cloud infrastructure,on-premises,QPT 1.1.9,Visual Merchandiser,product rule,functionality,filter, products,staging,updates,2.4.1,2.4.1-p1,2.4.2,2.4.2-p1,2.4.2-p2,2.4.3,2.4.3-p1
title: 'MDVA-37984: Visual Merchandiser not working correctly when staging updates are applied'
---

# MDVA-37984: Visual Merchandiser not working correctly when staging updates are applied

The MDVA-37984 patch solves the issue where the Visual Merchandiser's “Match product by rule” functionality does not filter products correctly when staging updates are applied. This patch is available when the [Quality Patches Tool (QPT)](https://support.magento.com/hc/en-us/articles/360047139492) 1.1.9 is installed. The patch ID is MDVA-37984. Please note that the issue is scheduled to be fixed in Adobe Commerce 2.4.5.

## Affected products and versions

**The patch is created for Adobe Commerce version:**

* Adobe Commerce (all deployment methods) 2.4.2

**Compatible with Adobe Commerce versions:**

* Adobe Commerce (all deployment methods) 2.4.1 - 2.4.3-p1

>[!NOTE]
>
>The patch might become applicable to other versions with new Quality Patches Tool releases. To check if the patch is compatible with your Adobe Commerce version, update the `magento/quality-patches` package to the latest version and check the compatibility on the [QPT landing page](https://devdocs.magento.com/quality-patches/tool.html#patch-grid). Use the patch ID as a search keyword to locate the patch.

## Issue

The Visual Merchandiser's “Match product by rule” functionality does not filter products correctly when staging updates are applied.

<u>Steps to reproduce</u>:

1. Create a schedule update for any existing product.
    * Set different values for `entity_id` and `row_id`.
1. Create a new configurable product and then a simple product (so the new product `entity_id` and `row_ids` are different as well).
    * To make it easier to replicate the issue, set a distinguishable qty value for the simple product - for example 5000.
1. Go to a category > **Products in category** and enable **Match products by rule**.
1. Now select "Quantity" as the attribute, "Greater" as the operator, and "4500" as the value.
1. Click **save**.

<u>Expected results</u>:

The newly created configurable product is listed.

<u>Actual results</u>:

The newly created configurable product is not listed.

## Apply the patch

To apply individual patches, use the following links depending on your deployment method:

* Adobe Commerce or Magento Open Source on-premises: [Software Update Guide > Apply Patches](https://devdocs.magento.com/guides/v2.4/comp-mgr/patching/mqp.html) in our developer documentation.
* Adobe Commerce on cloud infrastructure: [Upgrades and Patches > Apply Patches](https://devdocs.magento.com/cloud/project/project-patch.html) in our developer documentation.

## Related reading

To learn more about Quality Patches Tool, refer to:

* [Quality Patches Tool released: a new tool to self-serve quality patches](https://support.magento.com/hc/en-us/articles/360047139492) in our support knowledge base.
* [Check if patch is available for your Adobe Commerce issue using Quality Patches Tool](https://support.magento.com/hc/en-us/articles/360047125252) in our support knowledge base.

For info about other patches available in QPT, refer to [Patches available in QPT](https://devdocs.magento.com/quality-patches/tool.html#patch-grid) in our developer documentation.