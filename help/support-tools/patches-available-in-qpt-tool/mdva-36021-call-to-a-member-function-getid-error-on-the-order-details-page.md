---
description: The MDVA-36021 patch solves the issue where users get *Call to a member function getId()* error message when trying to open order details. This patch is available when the Quality Patches Tool (QPT) 1.1.1 is installed. The patch ID is MDVA-36021. Please note that the issue is scheduled to be fixed in Adobe Commerce 2.4.4.
labels: QPT patches,Quality Patches Tool,QPT,QPT,Quality Patches Tool,Support Tools,QPT 1.1.1,Magento Commerce,Magento Commerce Cloud,Adobe Commerce,on-premises,cloud infrastructure,Magento,orders,details,error message,2.4.0,2.4.0-p1,2.4.1,2.4.1-p1,2.4.2,2.4.2-p1
title: 'MDVA-36021: Users get error message when opening order details'
---

# MDVA-36021: Users get error message when opening order details

The MDVA-36021 patch solves the issue where users get *Call to a member function getId()* error message when trying to open order details. This patch is available when the [Quality Patches Tool (QPT)](https://support.magento.com/hc/en-us/articles/360047139492) 1.1.1 is installed. The patch ID is MDVA-36021. Please note that the issue is scheduled to be fixed in Adobe Commerce 2.4.4.

## Affected products and versions

**The patch is created for Adobe Commerce version:**

* Adobe Commerce on cloud infrastructure 2.4.1, 2.4.2

**Compatible with Adobe Commerce versions:**

* Adobe Commerce (all deployment methods) 2.4.0 - 2.4.2-p1

>[!NOTE]
>
>The patch might become applicable to other versions with new Quality Patches Tool releases. To check if the patch is compatible with your Adobe Commerce version, update the `magento/quality-patches` package to the latest version and check the compatibility on the [QPT landing page](https://devdocs.magento.com/quality-patches/tool.html#patch-grid). Use the patch ID as a search keyword to locate the patch.

## Issue

When users try to open order details, the following error message is displayed on the order details page in the Admin: *report.CRITICAL: Error: Call to a member function getId() on array in /magento2ce/app/code/Magento/Sales/view/adminhtml/templates/order/totals/tax.phtml:62*.

<u>Prerequisites</u>:

The system should have tax settings and orders with specific tax rates.

<u>Steps to reproduce</u>:

1. Log in to the Commerce Admin.
1. Go to **Sales** > **Orders** > **Open Order**.

<u>Expected results</u>:

The order is opened without any error.

<u>Actual results</u>:

You get an error message similar to the following: *report.CRITICAL: Error: Call to a member function getId() on array in /magento2ce/app/code/Magento/Sales/view/adminhtml/templates/order/totals/tax.phtml:62*.

## Apply the patch

To apply individual patches, use the following links depending on your deployment method:

* Adobe Commerce or Magento Open Source on-premises: [Software Update Guide > Apply Patches](https://devdocs.magento.com/guides/v2.4/comp-mgr/patching/mqp.html) in our developer documentation.
* Adobe Commerce on cloud infrastructure: [Upgrades and Patches > Apply Patches](https://devdocs.magento.com/cloud/project/project-patch.html) in our developer documentation.

## Related reading

To learn more about Quality Patches Tool, refer to:

* [Quality Patches Tool released: a new tool to self-serve quality patches](https://support.magento.com/hc/en-us/articles/360047139492) in our support knowledge base.
* [Check if patch is available for your Adobe Commerce issue using Quality Patches Tool](https://support.magento.com/hc/en-us/articles/360047125252) in our support knowledge base.

For info about other patches available in QPT, refer to [Patches available in QPT](https://devdocs.magento.com/quality-patches/tool.html#patch-grid) in our developer documentation.