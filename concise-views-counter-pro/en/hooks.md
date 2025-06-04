# 可用钩子（Hooks）

为了方便开发者扩展插件功能，插件提供了一些动作（actions）与过滤器（filters）。

## 动作钩子（Actions）

### `concise_post_views_counted`

在成功记录浏览量后触发。

```php
do_action('concise_post_views_counted', $post_id);
```

## 过滤器钩子（Filters）

### `concise_post_views_format`

自定义浏览量格式输出。

```php
add_filter('concise_post_views_format', function($output, $count) {
    return "<span>{$count} 次浏览</span>";
}, 10, 2);
```

- `$output`：默认的输出 HTML
- `$count`：浏览次数
