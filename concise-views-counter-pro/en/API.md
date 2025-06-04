# REST API 使用说明

插件提供了以下 REST API 接口，方便开发者二次集成和调用数据。

## 获取浏览量

**GET** `/wp-json/concise-post-views/v1/view-count?post_id=123`

- 参数：
  - `post_id`：文章 ID

- 返回示例：

```json
{
  "post_id": 123,
  "views": 57
}
```

## 增加浏览量

**POST** `/wp-json/concise-post-views/v1/increase`

- 参数（JSON）：

```json
{
  "post_id": 123
}
```

- 返回示例：

```json
{
  "success": true,
  "views": 58
}
```

确保已启用 REST API 模块。
