# REST API 接口文档

### 以下为 Concise Views Counter Pro 插件提供的 REST API 接口说明，用于获取文章的浏览量统计数据。

---

## 📌 接口地址

- GET /wp-json/cvcp/v1/views/{id}

##### **{id}** 是目标文章的 WordPress ID，例如：

##### GET https://yourdomain.com/wp-json/cvcp/v1/views/123


---

## 🧾 请求方式

- **HTTP 方法：** GET
- **是否需要认证：** 不需要登录用户，但必须激活专业版授权

---

## 🧱 请求参数

| 参数名 | 类型 | 必须 | 说明         |
| ------ | ---- | ---- | ------------ |
| `id`   | 整数 | 是   | 要查询的文章 ID |

---

## ✅ 正确响应示例

```json
{
  "post_id": 123,
  "total_views": 2789,
  "today_views": 35
}
```

## ❌ 错误响应示例（未激活授权）

```json
{
  "code": "cvcp_rest_pro_only",
  "message": "此功能仅限专业版用户使用。",
  "data": {
    "status": 403
  }
}
```

## 💡 使用示例

### 使用 cURL：

- curl https://yourdomain.com/wp-json/cvcp/v1/views/123

### 使用 JavaScript Fetch：

```
fetch('https://yourdomain.com/wp-json/cvcp/v1/views/123')
  .then(res => res.json())
  .then(data => console.log(data));
```

## 📦 版本说明

- 当前版本：v1

- 路由前缀：cvcp/v1

- 将来如需扩展可使用 cvcp/v2 等版本

## 🛠 备注

- 此接口仅用于读取统计数据，不会增加浏览量。

- 若文章设置为“不统计”，数据依旧可查询，但数值可能保持不变。