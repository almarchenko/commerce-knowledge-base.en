---
description: The MDVA-19391 patch solves the issue when an error in the PageBuilderAnalytics module prevents use of Advanced Reporting. This patch is available when the Quality Patches Tool (QPT) 1.0.13 is installed. Please note there is currently no solution in Adobe Commerce planned besides this patch.
labels: 2.3.1,2.3.2,2.3.2-p2,2.3.3,2.3.3-p1,2.3.4,2.3.4-p1,2.3.4-p2,404 error,Advanced Reporting,QPT 1.0.13,QPT patches,Magento Commerce,Magento Commerce Cloud,Quality Patches Tool,PageBuilderAnalytics module,Adobe Commerce,cloud infrastructure,on-premises
title: 'MDVA-19391: Advanced Reporting not working'
---

# MDVA-19391: Advanced Reporting not working

The MDVA-19391 patch solves the issue when an error in the PageBuilderAnalytics module prevents use of Advanced Reporting. This patch is available when the [Quality Patches Tool (QPT)](https://devdocs.magento.com/guides/v2.4/comp-mgr/patching.html#mqp) 1.0.13 is installed. Please note there is currently no solution in Adobe Commerce planned besides this patch.

## Affected products and versions

**The patch is created for Adobe Commerce version:**

Adobe Commerce on cloud infrastructure 2.3.1

**Compatible with Adobe Commerce versions:**

Adobe Commerce (all deployment methods) 2.3.1 - 2.3.4-p2

>[!NOTE]
>
>The patch might become applicable to other versions with new Quality Patches Tool releases. To check if the patch is compatible with your Adobe Commerce version, update the `magento/quality-patches` package to the latest version and check the compatibility on the [QPT landing page](https://devdocs.magento.com/quality-patches/tool.html#patch-grid). Use the patch ID as a search keyword to locate the patch.

## Issue

<u>Steps to reproduce</u>:

1. On the Admin sidebar, choose **Reports**.
1. Then under **Business Intelligence**, choose **Advanced Reporting**.

<u>Expected results</u>:

The **Advanced Reporting** report should load, as expected.

<u>Actual results</u>:

The *404 We can't find what you're looking for.* error page appears.

## Apply the patch

To apply individual patches, use the following links depending on your deployment method:

* Adobe Commerce or Magento Open Source on-premises: [Software Update Guide > Apply Patches](https://devdocs.magento.com/guides/v2.4/comp-mgr/patching/mqp.html) in our developer documentation.
* Adobe Commerce on cloud infrastructure: [Upgrades and Patches > Apply Patches](https://devdocs.magento.com/cloud/project/project-patch.html) in our developer documentation.

## Related reading

To learn more about Quality Patches Tool, refer to:

* [Quality Patches Tool released: a new tool to self-serve quality patches](https://support.magento.com/hc/en-us/articles/360047139492) in our support knowledge base.
* [Check if patch is available for your Adobe Commerce issue using Quality Patches Tool](https://support.magento.com/hc/en-us/articles/360047125252) in our support knowledge base.

For info about other patches available in QPT, refer to [Patches available in QPT](https://devdocs.magento.com/quality-patches/tool.html#patch-grid) in our developer documentation.