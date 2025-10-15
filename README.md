# WOOCOMMERCE ADDING SHIPPING PHONE — Basic Introduction

**WOOCOMMERCE ADDING SHIPPING PHONE** adds a dedicated **“Shipping phone”** field to the shipping address and enforces it **only when it matters**:

* **Conditional requirement**: the field becomes required when **(a)** the shipping name differs from the billing name **or (b)** the shipping country differs from the billing country.
* **Clean UI**: the label shows **“Shipping phone”** (no “(optional)” badge). A small JS enhancement toggles the required star (`*`) and HTML5 `required` attribute in real time based on the conditions above.
* **Order meta & compatibility**: the number is saved to order meta as **`_shipping_phone`** (HPOS-compatible).
* **Where it appears**:

  * WooCommerce **admin order page** (under the shipping address)
  * **Customer emails** (customer details section)
  * **Formatted shipping address** (thank you page / order view)
* **Zero-config**: no settings page; works out of the box.
* **Support/Publisher**: [www.elechouse.com](http://www.elechouse.com) · [elechouse@elechouse.com](mailto:elechouse@elechouse.com)

---

# Installation Guide

## A) Install via WordPress Admin (ZIP upload)

1. Download the plugin ZIP: **woocommerce-adding-shipping-phone-1.3.2.zip**.
2. In WordPress: **Plugins → Add New → Upload Plugin**.
3. Select the ZIP → **Install Now** → **Activate**.
4. If you use page/object caching (e.g., Redis), **clear caches**.

## B) Install via WP-CLI

```bash
wp plugin install /path/to/woocommerce-adding-shipping-phone-1.3.2.zip --activate
```

## C) Manual (FTP / File Manager)

1. Unzip the package locally.
2. Upload the folder **`woocommerce-adding-shipping-phone`** to:

   ```
   wp-content/plugins/woocommerce-adding-shipping-phone/
   ```
3. Go to **Plugins** in WP Admin and **Activate**.

---

## Post-Install Checklist (quick test)

1. Go to your **checkout** page and tick **“Ship to a different address”**.
2. Try either of the following, one at a time:

   * Make the **shipping name** different from the **billing name**; or
   * Choose a **shipping country** different from the **billing country**.
3. You should see a **required star** appear next to **Shipping phone**, and the browser should prevent submission if it’s empty.
4. Submit with a valid phone number. In **WooCommerce → Orders**, open the new order and confirm “**Shipping phone**” shows under the shipping address; also check the **customer email** and the **formatted shipping address** line.

---

## Requirements & Notes

* **WordPress** 5.8+; **PHP** 7.2+ (7.4+ recommended); **WooCommerce** current versions supported; HPOS-compatible.
* The plugin does not expose a settings page; the behavior above is enabled by default.
* Uninstall: simply **Deactivate** and **Delete** the plugin (existing orders will keep their `_shipping_phone` meta).

**Support**
Website: **[www.elechouse.com](http://www.elechouse.com)**
Email: **[elechouse@elechouse.com](mailto:elechouse@elechouse.com)**
