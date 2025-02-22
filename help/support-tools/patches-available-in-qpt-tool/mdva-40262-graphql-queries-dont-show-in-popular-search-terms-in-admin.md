---
description: The MDVA-40262 Adobe Commerce quality patch fixes the issue where GraphQL search queries are not shown in popular search terms in the admin. This patch is available when the Quality Patches Tool (QPT) 1.1.3 is installed. The patch ID is MDVA-40262. Please note that the issue is scheduled to be fixed in Adobe Commerce 2.4.4.
labels: support tools,QPT patches,Quality Patches Tool,Magneto Commerce Cloud,QPT 1.1.3,Adobe Commerce,cloud infrastructure,on-premises,2.4.2,2.4.2-p1,2.4.2-p2,2.4.3
title: 'MDVA-40262: GraphQL queries don''t show in popular search terms in admin'
---

# MDVA-40262: GraphQL queries don't show in popular search terms in admin

The MDVA-40262 Adobe Commerce quality patch fixes the issue where GraphQL search queries are not shown in popular search terms in the admin. This patch is available when the [Quality Patches Tool (QPT)](https://devdocs.magento.com/guides/v2.4/comp-mgr/patching.html#mqp) 1.1.3 is installed. The patch ID is MDVA-40262. Please note that the issue is scheduled to be fixed in Adobe Commerce 2.4.4.

## Affected products and versions

**The patch is created for Adobe Commerce version:**

Adobe Commerce (all deployment methods) 2.4.2-p1

**Compatible with Adobe Commerce versions:**

Adobe Commerce (all deployment methods) 2.4.2 – 2.4.3

>[!NOTE]
>
>The patch might become applicable to other versions with new Quality Patches Tool releases. To check if the patch is compatible with your Adobe Commerce version, update the `magento/quality-patches` package to the latest version and check the compatibility on the [QPT landing page](https://devdocs.magento.com/quality-patches/tool.html#patch-grid). Use the patch ID as a search keyword to locate the patch.

## Issue

GraphQL queries are not shown in popular search terms in the admin.

<u>Prerequisites</u>:

Sample data must be installed.

<u>Steps to reproduce</u>:

1. Go to **Stores** > **Configuration** > **Catalog** > **SEO** > **Popular Search Terms** and set to enable.
1. Run the following GraphQL query:

<pre>
<code class="language-graphql">
{
  products(
    search: "jackets"
    filter: { price: { to: "50" } }
    pageSize: 20
   ) {
    total_count
    items {
      name
      sku
    }
    page_info {
      page_size
      current_page
    }
  }
}
</code>
</pre>

<u>Expected results</u>:

After running the GraphQL query to search for a product, the search query should be added to popular search terms.

<u>Actual results</u>:

The search query is not added to popular search terms.

## Apply the patch

To apply individual patches, use the following links depending on your deployment type:

* Adobe Commerce or Magento Open Source on-premises: [Software Update Guide > Apply Patches](https://devdocs.magento.com/guides/v2.4/comp-mgr/patching/mqp.html) in our developer documentation.
* Adobe Commerce on cloud infrastructure: [Upgrades and Patches > Apply Patches](https://devdocs.magento.com/cloud/project/project-patch.html) in our developer documentation. 

## Related reading

To learn more about quality patches for Adobe Commerce, refer to:

* [Quality Patches Tool released: a new tool to self-serve quality patches](https://support.magento.com/hc/en-us/articles/360047139492).
* [Check if patch is available for your Adobe Commerce issue using Quality Patches Tool](https://support.magento.com/hc/en-us/articles/360047125252).

For info about other patches available in QPT, refer to the [Patches available in QPT](https://support.magento.com/hc/en-us/sections/360010506631-Patches-available-in-QPT-tool-) section.