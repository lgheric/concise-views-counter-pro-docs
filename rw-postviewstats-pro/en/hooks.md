# Available Hooks

To allow developers to extend plugin functionality, the plugin provides various actions and filters.

## Action Hooks
### `rw_cvc_post_view_count_updated`
Triggered after a post's view count is updated.

**Parameters**
- `$post_id` (int): Post ID
- `$new_view_count` (int): Updated view count
- `$old_view_count` (int): Previous view count

---

### `rw_cvc_settings_saved`
Triggered after plugin settings are saved.

**Parameters**
- `$new_settings` (array)
- `$old_settings` (array)

---

### `concise_post_views_counted`

Triggered after a view is successfully recorded.

```php
do_action('concise_post_views_counted', $post_id);
```

## Filter Hooks
### `rw_cvc_should_count_view`
Determines whether to count the current request as a view.

**Parameters**
- `$should_count` (bool): Default  `true`
- `$post_id` (int)

**Return**
- `bool`: Return `false`  to skip counting

---

### `rw_cvc_display_views_output`
Allows customization of the view count display format on the front end.
Filter the output of the [concise_post_views] shortcode for total views.

**Parameters**
- `$output` (string|int): The current views value (e.g. '123').
- `$post_id` (int) The current post ID.
- `$atts` (array)  The original shortcode attributes.

---

### `rw_cvc_rest_api_response`
Modifies the data returned by the REST API.

**Parameters**
- `$response_data` (array): Current response data
- `$post` (WP_Post):  Current post object

### `concise_post_views_format`

Customizes the view count output format.

```php
add_filter('concise_post_views_format', function($output, $count) {
    return "<span>{$count} 次浏览</span>";
}, 10, 2);
```

- `$output`：Default HTML output
- `$count`：View count

### `rw_cvc_display_views_output`  
  Modifies the view count output format.
  **Parameters**：  
  `$views` (string) - Original view count  
  `$post_id` (int) - Post ID  
  `$atts` (array) - Shortcode attributes  
  **Return**：Formatted string
  
```php
// 在主题的functions.php中添加：
add_filter('rw_cvc_display_views_output', function($views, $post_id) {
    return sprintf(
        '<span class="custom-views" data-views="%d">👁️ %s 次</span>',
        $views,
        number_format_i18n($views)
    );
}, 10, 2);
```

### `rw_cvc_rest_api_response`

Used to filter the REST API response data for the post views endpoint.

**Parameters**  
- `$response_data` (`array`): The data to be returned in the API response.  
- `$post` (`WP_Post`): The post object associated with the requested post ID.

**Return**  
- `array`: The modified response data that will be returned to the REST API caller.

**Usage Example**

```php
add_filter('rw_cvc_rest_api_response', function($data, $post) {
    $data['custom_note'] = 'This is additional data added via filter.';
    return $data;
}, 10, 2);
