---
description: The MDVA-42237 patch fixes the issue where the configurable product's special price is not updated after changes in its subproduct price. This patch is available when the Quality Patches Tool (QPT) 1.1.11 is installed. The patch ID is MDVA-42237. Please note that the issue is scheduled to be fixed in Adobe Commerce 2.4.5.
labels: QPT patches,Quality Patches Tool,Support Tools,Magento,Adobe Commerce,cloud infrastructure,on-premises,QPT 1.1.11,configurable product,GraphQL,2.4.2,2.4.2-p1,2.4.2-p2,2.4.3,2.4.3-p1
title: 'MDVA-42237: Configurable product special price not updated'
---

# MDVA-42237: Configurable product special price not updated

The MDVA-42237 patch fixes the issue where the configurable product's special price is not updated after changes in its subproduct price. This patch is available when the [Quality Patches Tool (QPT)](https://support.magento.com/hc/en-us/articles/360047139492) 1.1.11 is installed. The patch ID is MDVA-42237. Please note that the issue is scheduled to be fixed in Adobe Commerce 2.4.5.

## Affected products and versions

**The patch is created for Adobe Commerce version:**

* Adobe Commerce (all deployment methods) 2.4.2-p1

**Compatible with Adobe Commerce versions:**

* Adobe Commerce (all deployment methods) 2.4.2 - 2.4.3-p1

>[!NOTE]
>
>The patch might become applicable to other versions with new Quality Patches Tool releases. To check if the patch is compatible with your Adobe Commerce version, update the `magento/quality-patches` package to the latest version and check the compatibility on the [QPT landing page](https://devdocs.magento.com/quality-patches/tool.html#patch-grid). Use the patch ID as a search keyword to locate the patch.

## Issue

The configurable product's special price is not updated after changes in its subproduct price.

<u>Steps to reproduce</u>:

1. Go to **Admin** > **System** > **Index Management** and set **Index Mode** to **Update By Schedule** for all indexes.
1. Create a configurable product with one simple product and set a special price for the subproduct.
1. Check that the special price is reflected on the Storefront.
1. Remove the special price using GraphQL and recheck the product price on the Storefront.

<u>Expected results</u>:

The special price is no longer displayed on the Storefront.

<u>Actual results</u>:

The price is not updated on the Storefront.

## Apply the patch

To apply individual patches, use the following links depending on your deployment method:

* Adobe Commerce or Magento Open Source on-premises: [Software Update Guide > Apply Patches](https://devdocs.magento.com/guides/v2.4/comp-mgr/patching/mqp.html) in our developer documentation.
* Adobe Commerce on cloud infrastructure: [Upgrades and Patches > Apply Patches](https://devdocs.magento.com/cloud/project/project-patch.html) in our developer documentation.

## Related reading

To learn more about Quality Patches Tool, refer to:

* [Quality Patches Tool released: a new tool to self-serve quality patches](https://support.magento.com/hc/en-us/articles/360047139492) in our support knowledge base.
* [Check if patch is available for your Adobe Commerce issue using Quality Patches Tool](https://support.magento.com/hc/en-us/articles/360047125252) in our support knowledge base.

For info about other patches available in QPT, refer to [Patches available in QPT](https://devdocs.magento.com/quality-patches/tool.html#patch-grid) in our developer documentation.