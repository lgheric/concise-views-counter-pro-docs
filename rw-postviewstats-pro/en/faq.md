## Frequently Asked Questions

**How to reset the view count?**

Go to the settings page and click the "Reset View Count" button.

**Can this plugin track views of custom post types?**
Yes. By default, it tracks the **'post'**and **'page'**types. You can add support for any custom post type using a filter hook in your theme or another plugin:
```php
add_filter('rw_cvc_supported_post_types', function($types) {
    $types[] = 'your_custom_post_type';
    return $types;
});
````
**How are duplicate views prevented?**
Uses browser cookies to ignore repeat visits for 12 hours (configurable via JS).

**Can I export view data?**
Yes! Pro version supports CSV exports by post/date range.

**Is my personal data transmitted or stored?**
Some data such as IP address and admin email may be transmitted over HTTPS for license validation, but we do not store this data in identifiable form. All sensitive information is hashed or anonymized before storage.

**How to add translations?**
Copy `/languages/rw-postviewstats-pro.pot` and submit your `.po` file.

