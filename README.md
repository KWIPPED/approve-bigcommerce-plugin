# APPROVE for BigCommerce


---
- [BigCommerce Overview](#overview)
- [BigCommerce Theme Integration Details](#theme-integration)
	- [Step 1: Add Plugin Snippet](#step1)
	- [Step 2: Retrieve & Add Plugin Code](#step4)
	- [Step 3: Add Product Button](#step8)
	- [Step 4: Set Needed Settings](#step6)
	- [Step 5: Add Process Triggers](#step9)
	- [Step 6: Done](#step10)
- [BigCommerce Custom Integration Details](#custom-integration)


<a name="overview"></a>

## BigCommerce Overview

Integrating APPROVE into your BigCommerce site is fairly straight forward. We have options created to cater to every level of expertise,
and every business size. The following 
table will help you choose the right BigCommerce integration solution for your business.

<!-- 
Options to build out:

|APPROVE Landing Page Link Integration|<larecipe-progress type="success" :value="40"></larecipe-progress>|<i class="fa fa-check"/>|Familiarity with basic BigCommerce theme customization|
|BigCommerce App Extension|<larecipe-progress type="success" :value="30"></larecipe-progress>|<i class="fa fa-check"/>|Familiarity with basic BigCommerce theme customization|
|BigCommerce App|<larecipe-progress type="success" :value="20"></larecipe-progress>|<i class="fa fa-check"/>|Familiarity with basic BigCommerce theme customization|
|BigCommerce Section|<larecipe-progress type="success" :value="20"></larecipe-progress>|<i class="fa fa-check"/>|Familiarity with basic BigCommerce theme customization|

-->
|BigCommerce Solution|Technical Level|Integration Into Your Site|Requirements|
|----|:---:|:---:|---|
|BigCommerce Theme Integration|<larecipe-progress type="success" :value="70"></larecipe-progress>|<i class="fa fa-check"/>|Familiarity with basic BigCommerce theme customization and an understanding of basic to intermediate javascript / jquery is needed|
|Custom (We create a solution specifically for you)|<larecipe-progress type="success" :value="0"></larecipe-progress>|<i class="fa fa-check"/>|Contact KWIPPED for a quote|
<!--
> {primary} Primary .<


## 
> {success} Success .


## 
> {info} Info .


## 
> {danger} Danger .


## 
>{warning} Warning .
-->

<a name="theme-integration"></a>

## BigCommerce Theme Integration Details

The steps needed to integrate with the shopify theme are summed up below. 

1. <a href="#step1">Add the contents of `approve-bigcommerce-plugin.html` into BigCommerce</a>
2. <a href="#step2">Retrieve your APPROVE code snippet</a>
5. <a href="#step3">Place the APPROVE finance button code in the BigCommerce cart and product page(s).</a>
3. <a href="#step4">Edit the `approveOpt` settings as needed</a>
6. <a href="#step5">Add a jquery or javascript trigger if needed.</a>
7. <a href="#step6">Done.</a>

> {danger} The following code and information are <b>EXAMPLES ONLY</b> and should only be used as a general reference. 
> Due to the complexities of BigCommerce and inconsistencies in variable naming and structure from theme to theme you should consult with a developer who is very familiar with BigCommerce and javascript/jquery to integrate. 


<a name="step1"></a>

### STEP 1: Add the contents of `approve-plugin.html` into BigCommerce

GoTo: Admin Dashboard -> Storefront -> Script Manager

- Click on "Create a Script"
- Give this script a name something like "APPROVE-Plugin-Script"
- Give the script a helpful description. 
- Under "Location on page" choose `footer`
- Under "Select pages where script will be added" choose `Store pages`
- Under "Script category" choose `Functional`
- Under "Script type" chose `script`
- Under "Script contents" copy the contents of <a target="_blank" href="https://raw.githubusercontent.com/KWIPPED/approve-bigcommerce-plugin/master/dist/approve-bigcommerce-plugin.html" >`approve-bigcommerce-plugin.html`</a>, or copy the block below and paste its contents in this section. 
<div id="load_approve_bigcommerce_plugin_html" class="load_file_content" data-highlightlang="html" data-url="https://raw.githubusercontent.com/KWIPPED/approve-bigcommerce-plugin/master/dist/approve-bigcommerce-plugin.html"></div>
- Click "Save" 





 <!-- <larecipe-button tag="a" href="shopify" type="blue" class="mx-2 px-4"><i class="fab fa-github"></i></larecipe-button> -->



<hr />

<a name="step2"></a>

### STEP 2: Retrieve your APPROVE code snippet

> {warning}
> ### Before you add your APPROVE code snippet you must first insure that you are using a copied theme for your site so that your additions are not overwritten. 
> ### If your theme is not a copy you need to make a copy before you can continue. 
> - To make a copy of your theme, go into the Admin Dashboard -> Storefront -> My Themes
> - With the currently selected theme, click on "Advanced" and go down to "Make a Copy" 
> - Once the copy has been made you can make it your current theme. 

<br />

Retrieve your APPROVE `<approve-widget></approve-widget>` code snippet from KWIPPED

1. Log into <a href="https://www.kwipped.com">KWIPPED</a> and go to `APPROVE Plugin Configurator` in `APPROVE > Settings`.

2. Locate the section `Copy Plugin Code` 

3. In the box below the `Copy Plugin Code` header, select the entire section of code for `<approve-widget></approve-widget>` and copy it to your clipboard

4. In your BigCommerce Admin Dashboard GoTo: Admin Dashboard -> Storefront -> My Themes

5. In the active theme click on "Advanced"  and select "Edit Theme Files"

6. The main template should be in a folder labeled `templates` and inside there, either in that directory or in a directory named `layout`, you should see a file named something like `base.html`, `default.html` or `products.html`

> {info}
> If you want the plugin to appear on the cart, you will need to place the `<approve-widget></approve-widget>` tag on either the master template that is used for both products and carts OR you will have to also include it in the cart template. 

7. Once you determine the template file that is loaded for your main product pages and/or cart pages, open it in the editor. 

8. Look for the tag `@{{{footer.scripts}}}` inside the template file and paste your APPROVE code snippet right above this tag. 

9. Save the changes to the template. 

At this point the widget has been added to the template. Now we need to add in the buttons in the appropriate places.

<hr />


<a name="step3"></a>

### STEP 3: Place the APPROVE finance button code in the BigCommerce product and cart page(s).


Place the APPROVE finance cart button snippet code found in the file <a target="_blank" href="https://raw.githubusercontent.com/KWIPPED/approve-bigcommerce-plugin/master/dist/approve-button-cart-template-example.html" >`approve-button-cart-template-example.html`</a> in the appropriate BigCommerce cart theme file where you want the APPROVE finance button to appear.

<div id="load_approve_button_cart_template_example_html" class="load_file_content" data-highlightlang="javascript" data-url="https://raw.githubusercontent.com/KWIPPED/approve-bigcommerce-plugin/master/dist/approve-button-cart-template-example.html"></div>

Place the APPROVE finance product button snippet code found in the file <a target="_blank" href="https://raw.githubusercontent.com/KWIPPED/approve-bigcommerce-plugin/master/dist/approve-button-price-template-example.html" >`approve-button-price-template-example.html`</a> in the appropriate BigCommerce product theme file where you want the APPROVE finance button to appear.

<div id="load_approve-button-price-template-example.html" class="load_file_content" data-highlightlang="html" data-url="https://raw.githubusercontent.com/KWIPPED/approve-bigcommerce-plugin/master/dist/approve-button-price-template-example.html"></div>

EXAMPLE PRICE BUTTON OPTIONS: 

### Price Range Template File
Place the APPROVE finance product button snippet code found in the file <a target="_blank" href="https://raw.githubusercontent.com/KWIPPED/approve-bigcommerce-plugin/master/dist/approve-button-price-range-template-example.html" >`approve-button-price-range-template-example.html`</a> in the appropriate BigCommerce product theme file where you want the APPROVE finance button to appear.

<div id="load_approve-button-price-range-template-example.html" class="load_file_content" data-highlightlang="html" data-url="https://raw.githubusercontent.com/KWIPPED/approve-bigcommerce-plugin/master/dist/approve-button-price-range-template-example.html"></div>

### Product View
Place the APPROVE finance product button snippet code found in the file <a target="_blank" href="https://raw.githubusercontent.com/KWIPPED/approve-bigcommerce-plugin/master/dist/approve-button-product-view-template-example.html" >`approve-button-product-view-template-example.html`</a> in the appropriate BigCommerce product theme file where you want the APPROVE finance button to appear.

<div id="load_approve-button-product-view-template-example.html" class="load_file_content" data-highlightlang="html" data-url="https://raw.githubusercontent.com/KWIPPED/approve-bigcommerce-plugin/master/dist/approve-button-product-view-template-example.html"></div>


<hr />

<a name="step4"></a>

### STEP 4: Edit the `config` settings as needed

Set the appropriate jquery element tags needed in the javascript object `kwipped_approve.bc_app.config`

To do this you will need to edit the Script added in the first step under `Admin Dashboard -> Storefront -> Script Manager`

Locate the following section in this script:


```javascript
	kwipped_approve.bc_app.config = {
		button_amt_threshold: 2000,
		cart_amt_threshold: 2000,
		product_info_wrap: ".productView",
		product_price_ele: ".productView [data-product-price-without-tax]:first",
		qty_ele: 'input[name="qty[]"]',
		qty_down_ele: 'button[data-action="dec"]',
		qty_up_ele: 'button[data-action="inc"]',
	}
```

- `button_amt_threshold`: This should be set to the product price minimum to show the APPROVE finance button. 
- `cart_amt_threshold`: This should be set to the cart price minimum to show the APPROVE finance button. 
- `product_info_wrap`: Set to product view wrapping element that contians both the APPROVE finance button as well as the qty and price elements. 
- `product_price_ele`: Set to the price element jquery ID or class tag to retrieve the base price on a single APPROVE finance button product page. 
- `qty_ele`: Set to the quantity element jQuery class or ID tag that contains the qty increase/decrease selectors. 
- `qty_down_ele`: Set to quantity down click element jquery class tag to set the current quantity for the APPROVE finance button. 
- `qty_up_ele`: Set to quantity up click element jquery class tag to set the current quantity for the APPROVE finance button.  

<hr />


<a name="step5"></a>

### STEP 5: Add a jquery or javascript trigger if needed.

To fully integrate into a BigCommerce theme, you will want to create custom code to handle any option changes or any additions to the products attached to a APPROVE finance button. This can be done with javascript/jQuery and update the buttons accordingly. 

The below is an example of how to attach the qty up/down click into the APPROVE finance button (a modified version of this code is at the time of this writing included in the approve-bigcommerce-plugin.html file):


```javascript

var cur_qty_count = 1; // set to starting qty for product

$(" #qty_down_button ").click(function () {
	cur_qty_count = (cur_qty_count > 1) ? Number(cur_qty_count) - 1 : 1;
	if (product_approve_single_button.length > 0) {
		product_approve_single_button.attr("approve-qty", cur_qty_count);
		kwipped_approve.bc_app.approve_button_show_hide(product_approve_single_button);
	}
});

$(" #qty_up_button ").click(function () {
	cur_qty_count = Number(cur_qty_count) + 1;
	if (product_approve_single_button.length > 0) {
		product_approve_single_button.attr("approve-qty", cur_qty_count);
		kwipped_approve.bc_app.approve_button_show_hide(product_approve_single_button);
	}
});

```


<a name="step6"></a>

### STEP 6: Done.




<a name="custom-integration"></a>

## BigCommerce Theme Integration Details

### Contact KWIPPED for a quote

<!--
![APPROVE API Screenshot](/images/API_shot.png)
-->

