# Concise Views Counter Pro (CVCP) - User Guide

**Plugin Version:** 1.0.0  
**Compatible with WordPress:** 6.8  
**Minimum PHP Version:** 8.2  
**Minimum MySQL Version:** 5.7  
**Summary:** A multisite-supported view counter and data management tool for WordPress.

---

## 1. Installation & Configuration

### Installation Methods

- **Free Version:** Available in the WordPress plugin directory or via manual ZIP upload.
- **Pro Version:** Downloadable from Codecanyon.net. Install manually via ZIP upload in WordPress.

### Initial Setup

- After activation, the plugin starts working immediately.
- An optional **Settings** button is available next to the plugin entry in the WordPress admin panel.

### Multisite

- Requires **Network Admin** privileges.
- Fully compatible with WordPress Multisite architecture.

---

## 2. Feature Modules

### 2.1 View Counter

- **Supports:** Posts, Pages, Custom Post Types.
- **Excludes:** Attachments and WooCommerce products (by default).
- **Anti-Duplication Logic:** Avoids counting reloads by the same user in a short period.
- **User Scope:** Differentiates between logged-in users and guests.
- **Tracking Method:** Automatically integrated — no manual code insertion required.

---

### 2.2 Data Management

#### Cleaning

- **Criteria:** Clean data by date range or post type.
- **Safety:** Preview and confirm before deletion.

#### Export

- **Formats:** CSV and JSON.
- **Fields:** URL, View Count, Date Range, Post Type, and more.

---

### 2.3 Shortcodes

Example:
```shortcode
[top_views limit="5" post_type="post"]
```

- **Parameters:**
  - `limit` — Number of posts to display.
  - `post_type` — Post type filter (e.g., post, page).
- **Theme Dependency:** Not required.

---

### 2.4 REST API

- **Endpoint Example:**
  ```
  /wp-json/cvcp/v1/stats
  ```

- **Authentication:** Basic Auth or WordPress REST authentication.
- **Sample JSON Response:**
```json
{
  "post_id": 123,
  "views": 456,
  "url": "https://example.com/sample-post",
  "title": "Sample Post"
}
```

---

### 2.5 Multisite Support

- **Per-Site Tracking:** Each site maintains its own view counts.
- **Network Admin View:** Super admins can view and manage statistics across the entire network.

---

## Support

For more details, licensing, or updates, visit [Codecanyon - CVCP](https://codecanyon.net/).

