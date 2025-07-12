# 📦 View Count Data Cleaner - User Guide (Concise Views Counter Pro)

## Overview

The Data Cleaner allows you to **delete old view count records** to reduce database size and improve site performance.

You can clean data by **Post Type** and optionally by **Date Limit**. The Pro version supports cleaning custom post types as well.

---

## 🔧 How to Use

1. Go to your WordPress Dashboard → **Tools → Clear View Count Data**
2. Select the **Post Type** you want to clean.
3. (Optional) Enter a **Date Limit** in the format `YYYYMMDD`
   - Only records **older than this date** will be deleted.
   - Example: Entering `20250501` will delete records **before May 1, 2025**.
4. Click **[Clean up now]** to execute the cleanup.

---

## 💡 Examples

| Setting                        | Result                                                  |
|-------------------------------|---------------------------------------------------------|
| Post Type: `post`             | Cleans all view records of blog posts                   |
| Post Type: `post` + Date: `20240601` | Cleans only post views **before June 1, 2024**   |
| Post Type: `product`          | (Pro Only) Cleans WooCommerce product views             |

---

## 🔐 Feature Restrictions

| Feature                                      | Lite Version        | Pro Version         |
|---------------------------------------------|---------------------|---------------------|
| Clean `post` (Blog Posts)                   | ✅ Available        | ✅ Available        |
| Clean `page` (Pages)                        | ✅ Available        | ✅ Available        |
| Clean custom post types (e.g. product, portfolio) | ❌ Not available    | ✅ Available        |
| Custom date limit input                     | ❌ Fixed to 30 days ago | ✅ Fully configurable |

> 🔔 **Lite users** can only clean records for "posts" and "pages", and are limited to **cleaning data older than 30 days**.  
> **Pro users** can clean **any post type** with **any date range**.

---

## 🛡️ Safety Notice

- This action **cannot be undone**. Please double-check your selection before clicking "Clean up now".
- The plugin includes built-in permission checks and nonce validation for security.

---

## 🚀 Upgrade to Pro

Want to clean view records for products, portfolios, or other custom content types?  
Upgrade to Pro and unlock full control over your view data!

👉 [The purchase link will be provided here after the Pro version is released.](#)

---
