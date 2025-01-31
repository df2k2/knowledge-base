---
title: "MDVA-36138: free shipping rule not applied cart multiple items"
labels: 2.3.2,2.3.2-p2,2.3.3,2.3.3-p1,2.3.4,2.3.4-p2,2.3.5-p1,2.3.5-p2,2.3.6,2.3.6-p1,2.4.0,2.4.0-p1,2.4.1,2.4.1-p1,2.4.2,QPT 1.0.21,QPT patches,Magento Commerce,Magento Commerce Cloud,cart_rules,coupon,price,shipping,support tools
---

The MDVA-36138 Magento patch fixes the issue where when there are multiple items in the cart, the matching SKU in the Free Shipping is not getting free shipping applied to it. This patch is available when the [Quality Patches Tool (QPT)](https://support.magento.com/hc/en-us/articles/360047139492) 1.0.21 is installed. The patch ID is MDVA-36138. Please note that the issue was scheduled to be fixed in Magento 2.4.3.

## Affected products and versions

 **The patch is created for Magento version:** Magento Commerce Cloud 2.3.4

 **Compatible with Magento versions:** Magento Commerce and Magneto Commerce Cloud 2.3.2 and above

>![info]
>
 >Note: the patch might become applicable to other versions with new Quality Patches Tool releases. To check if the patch is compatible with your Adobe Commerce version, update the `magento/quality-patches` package to the latest version and check the compatibility on the [QPT landing page](https://devdocs.magento.com/quality-patches/tool.html#patch-grid). Use the patch ID as a search keyword to locate the patch.

## Issue

If a free shipping rule is applied to only specific items, the discount doesn't apply when there are other items in the cart.

 <span class="wysiwyg-underline">Steps to reproduce:</span> 

<ol><li>Create simple products - simple1 and simple2.</li><li>Configure USPS (or any online shipping method):<ul>
<li>
<strong>Allowed Methods</strong>:<em>Priority Mail</em>(one method selected for the purpose of not having a long list of methods in cart and checkout).</li>
<li>
<strong>Free Method</strong>:<em>Priority Mail</em>.</li>
</ul>
</li><li>Create a shopping cart rule:<ul>
<li>Specify coupon code</li>
<li>Conditions tab: leave empty</li>
<li>Actions tab:<div>
<div>
<pre>Condition: SKU is simple1
Free Shipping: For matching items only</pre>
</div>
</div>
</li>
</ul>
</li></ol>

1. Add simple1 to the cart.
1. Apply the coupon code.
1. Add simple2 to the cart.

 <span class="wysiwyg-underline">Actual result:</span> 

Shipping price includes simple1 and simple2.

 <span class="wysiwyg-underline">Expected result:</span> 

* simple1 - should have free shipping.
* simple2 - shipping should be paid.

## Apply the patch

For instructions on how to apply an QPT patch, use the following links depending on your Magento product:

* Magento Commerce: DevDocs [Apply patches using Quality Patches Tool](https://devdocs.magento.com/guides/v2.4/comp-mgr/patching/mqp.html) .
* Magento Commerce Cloud: DevDocs [Upgrades and Patches > Apply patches](https://devdocs.magento.com/cloud/project/project-patch.html) .

## Related reading

To learn more about Quality Patches Tool, refer to:

* [Quality Patches Tool released: a new tool to self-serve quality patches](https://support.magento.com/hc/en-us/articles/360047139492) .
* [Check if patch is available for your Magento issue using Quality Patches Tool](https://support.magento.com/hc/en-us/articles/360047125252) .

For info about other patches available in QPT tool, refer to the [Patches available in QPT tool](https://support.magento.com/hc/en-us/sections/360010506631-Patches-available-in-QPT-tool-) section.