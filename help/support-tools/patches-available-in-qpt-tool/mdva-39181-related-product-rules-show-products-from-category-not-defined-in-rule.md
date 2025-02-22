---
description: The MDVA-39181 patch solves the issue where related product rules show products from a category not defined in the rule. This patch is available when the Quality Patches Tool (QPT) 1.1.10 is installed. The patch ID is MDVA-39181. Please note that the issue is scheduled to be fixed in Adobe Commerce 2.4.5.
labels: QPT patches,Quality Patches Tool,Support Tools,QPT 1.1.10,Magento,category,Adobe Commerce,cloud infrastructure,on-premises,2.4.1,2.4.1-p1,2.4.2,2.4.2-p1,2.4.2-p2,2.4.3,2.4.3-p1
title: 'MDVA-39181: Related product rules show products from category undefined in rule'
---

# MDVA-39181: Related product rules show products from category undefined in rule

The MDVA-39181 patch solves the issue where related product rules show products from a category not defined in the rule. This patch is available when the [Quality Patches Tool (QPT)](https://support.magento.com/hc/en-us/articles/360047139492) 1.1.10 is installed. The patch ID is MDVA-39181. Please note that the issue is scheduled to be fixed in Adobe Commerce 2.4.5.

## Affected products and versions

**The patch is created for Adobe Commerce version:**

* Adobe Commerce (all deployment methods) 2.4.2

**Compatible with Adobe Commerce versions:**

* Adobe Commerce (all deployment methods) 2.4.1 - 2.4.3-p1

>[!NOTE]
>
>The patch might become applicable to other versions with new Quality Patches Tool releases. To check if the patch is compatible with your Adobe Commerce version, update the `magento/quality-patches` package to the latest version and check the compatibility on the [QPT landing page](https://devdocs.magento.com/quality-patches/tool.html#patch-grid). Use the patch ID as a search keyword to locate the patch.

## Issue

Related product rules show products from categories not defined in the rule.

<u>Prerequisites</u>:

Install sample data.

<u>Steps to reproduce</u>:

1. Create an attribute brand and add it to the **Tops Attribute Set**.
1. Choose **Josie**, **Augusta**, and **Ingrid** jackets to add to the Brand Kitty from **Women** > **Tops** > **Jackets category**.
1. Choose **Beaumont**, **Hyperion**, and **Kenobi** jackets to add to the Brand Kitty from **Men** > **Tops** > **Jacket category**.
1. Create a related product with:

    ```markdown
    Apply To: Related Products
    Customer Segments: All
    ```

    * Products to Match:

    ```markdown
    If ALL of these conditions are TRUE
      Category is {}
      Brand is {}
    ```

    * Products to Display:

    ```markdown
    If ALL of these conditions are TRUE
       Product Category is the same as Matched Product Category
       Product brand is Matched Product Brand
    ```

1. Open SKU WJ04 from the front end and check related products.
1. Update the category ID from **Women** > **Tops** > **Jackets** in case it is different from this.

<u>Expected results</u>:

Only products from the same brand and same child category are shown in related products.

<u>Actual results</u>:

Related products are shown of the same brand but from a random parent category.

## Apply the patch

To apply individual patches, use the following links depending on your deployment method:

* Adobe Commerce or Magento Open Source on-premises: [Software Update Guide > Apply Patches](https://devdocs.magento.com/guides/v2.4/comp-mgr/patching/mqp.html) in our developer documentation.
* Adobe Commerce on cloud infrastructure: [Upgrades and Patches > Apply Patches](https://devdocs.magento.com/cloud/project/project-patch.html) in our developer documentation.

## Related reading

To learn more about Quality Patches Tool, refer to:

* [Quality Patches Tool released: a new tool to self-serve quality patches](https://support.magento.com/hc/en-us/articles/360047139492) in our support knowledge base.
* [Check if patch is available for your Adobe Commerce issue using Quality Patches Tool](https://support.magento.com/hc/en-us/articles/360047125252) in our support knowledge base.

For info about other patches available in QPT, refer to [Patches available in QPT](https://devdocs.magento.com/quality-patches/tool.html#patch-grid) in our developer documentation.