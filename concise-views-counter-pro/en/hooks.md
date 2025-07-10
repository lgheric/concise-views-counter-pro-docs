# 可用钩子（Hooks）

为了方便开发者扩展插件功能，插件提供了一些动作（actions）与过滤器（filters）。

## 动作钩子（Actions）
### `rw_cvc_post_view_count_updated`
当文章的浏览量被更新后触发。

**参数**
- `$post_id` (int): 文章 ID
- `$new_view_count` (int): 更新后的浏览量
- `$old_view_count` (int): 更新前的浏览量

---

### `rw_cvc_settings_saved`
当插件设置保存后触发。

**参数**
- `$new_settings` (array)
- `$old_settings` (array)

---

### `concise_post_views_counted`

在成功记录浏览量后触发。

```php
do_action('concise_post_views_counted', $post_id);
```

## 过滤器钩子（Filters）
### `rw_cvc_should_count_view`
用于判断是否统计当前请求的浏览量。

**参数**
- `$should_count` (bool): 默认 `true`
- `$post_id` (int)

**返回**
- `bool`: 返回 `false` 跳过统计

---

### `rw_cvc_display_views_output`
允许自定义前台显示的浏览量格式。
Filter the output of the [concise_post_views] shortcode for total views.

**参数**
- `$output` (string|int): The current views value (e.g. '123').
- `$post_id` (int) The current post ID.
- `$atts` (array)  The original shortcode attributes.

---

### `rw_cvc_rest_api_response`
用于修改 REST API 返回的数据。

**参数**
- `$response_data` (array): 当前响应数据
- `$post` (WP_Post): 当前文章对象

### `concise_post_views_format`

自定义浏览量格式输出。

```php
add_filter('concise_post_views_format', function($output, $count) {
    return "<span>{$count} 次浏览</span>";
}, 10, 2);
```

- `$output`：默认的输出 HTML
- `$count`：浏览次数

### `rw_cvc_display_views_output`  
  修改浏览量输出格式  
  **参数**：  
  `$views` (string) - 原始浏览量  
  `$post_id` (int) - 文章ID  
  `$atts` (array) - 短码属性  
  **返回**：格式化后的字符串
  
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
