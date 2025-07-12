# REST API Documentation

The plugin provides the following REST API endpoints for developers to integrate and retrieve data.

## Get View Count ![Lite](https://img.shields.io/badge/Lite-green)

**GET** `/wp-json/rw-cvc/v1/views/{post_id}`

- Parameters：
  - `post_id`：Post ID

- Example response：

```json
{
  "post_id": 123,
  "views": 57
}
```

## Get View Count ![Pro](https://img.shields.io/badge/Pro-purple) ![Lifetime](https://img.shields.io/badge/Lifetime-gold)

**GET** `/wp-json/rw-cvc/v1/views/{post_id}?days=7`

- Parameters：
  - `post_id`：Post ID
  - `days`： Time period in days


- Example response：
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



## Increase View Count ![Pro](https://img.shields.io/badge/Pro-purple) ![Lifetime](https://img.shields.io/badge/Lifetime-gold)

**POST** `/wp-json/rw-cvc/v1/increase/{post_id}`

- Parameters：
  - `post_id`：Post ID

- Example response：

```json
{
  "success": true,
  "views": 58
}
```

Ensure the REST API feature is enabled.
