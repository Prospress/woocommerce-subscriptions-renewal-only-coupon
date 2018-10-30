# WooCommerce Subscriptions - Renewal Only Coupon

Only allow some coupons to be applied only to renewal payments, not initial sign-ups, by customers via the cart.

To define the coupon codes that should be renewal only, set the `WCS_RENEWAL_ONLY_COUPON_CODES` constant. The value fo the constant should be an array of coupon codes.

Store managers can still apply Renewal Only coupons to any order or subscription. Customers can only apply them to renewal order payments.

## Usage

### Option 1: Enter Coupon Codes via Subscriptions Settings

1. Go to **WooCommerce > Settings > Subscriptions**
1. Scroll to the **Renewals** section
1. Click the **Renewal Only Coupons** text field
1. Enter a coupon code to restrict to renewal payments only
1. If additional coupon codes are requireed, enter a comma (`, `) before each additional code

![](http://pic.pros.pr/0f138b7a4d9d/Screen%20Shot%202018-10-30%20at%2010.54.38.png)

### Option 2: Define Coupon Codes in Class Constant

```php
define( 'WCS_RENEWAL_ONLY_COUPON_CODES', array( 'coupon_code_one', 'hallowoon', 'cyber_monday' )  );
```

### Option 3: Define Coupon Codes via Filter

```php
function eg_my_renewal_only_coupon_codes( $existing_codes ) {

	$existing_codes[] = 'my_new_code';
	$existing_codes[] = 'my_other_new_code';

	return $existing_codes;
}
add_filter( 'wcs_renewal_only_coupon_codes', 'eg_my_renewal_only_coupon_codes' );
```

## Installation

To install:

1. Download the latest version of the plugin [here](https://github.com/Prospress/woocommerce-subscriptions-renewal-only-coupon/archive/master.zip)
1. Go to **Plugins > Add New > Upload** administration screen on your WordPress site
1. Select the ZIP file you just downloaded
1. Click **Install Now**
1. Click **Activate**

### Updates

To keep the plugin up-to-date, use the [GitHub Updater](https://github.com/afragen/github-updater).

## Requirements

This plugin requires:

* PHP 5.6 or newer
* WooCommerce 3.2.0 or newer
* WooCommerce Subscriptions 2.4.0 or newer

## Reporting Issues

If you find an problem or would like to request this plugin be extended, please [open a new Issue](https://github.com/Prospress/woocommerce-subscriptions-renewal-only-coupon/issues/new).

---

<p align="center">
	<a href="https://prospress.com/">
		<img src="https://cloud.githubusercontent.com/assets/235523/11986380/bb6a0958-a983-11e5-8e9b-b9781d37c64a.png" width="160">
	</a>
</p>