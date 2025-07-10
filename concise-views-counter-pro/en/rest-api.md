# REST API 使用说明

插件提供了以下 REST API 接口，方便开发者二次集成和调用数据。

## 获取浏览量 ![Lite](https://img.shields.io/badge/Lite-green)

**GET** `/wp-json/rw-cvc/v1/views/{post_id}`

- 参数：
  - `post_id`：文章 ID

- 返回示例：

```json
{
  "post_id": 123,
  "views": 57
}
```

## 获取浏览量 ![Pro](https://img.shields.io/badge/Pro-purple)

**GET** `/wp-json/rw-cvc/v1/views/{post_id}?days=7`

- 参数：
  - `post_id`：文章 ID
  - `days`： 天数


- 返回示例：
```json
{
  "post_id": 123,
  "total_views": 1578,
  "daily_views": {
    "2025-07-01": 300,
    "2025-07-02": 220
  }
}
```



## 增加浏览量 ![Pro](https://img.shields.io/badge/Pro-purple)

**POST** `/wp-json/rw-cvc/v1/increase/{post_id}`

- 参数：
  - `post_id`：文章 ID

- 返回示例：

```json
{
  "success": true,
  "views": 58
}
```

确保已启用 REST API 模块。
