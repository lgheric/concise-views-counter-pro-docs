# 📊 Data Export Feature Guide

The **Concise Views Counter Pro** plugin provides a simple way to export page view data as a CSV file. This helps you analyze, back up, or migrate your post and page traffic data.

This feature includes both **Lite** and **Pro** user functionality, with clear distinctions shown below.

---

## 🧭 How to Use the Export Feature

1. Log into your WordPress dashboard.

2. Go to the menu:
   ```
   Settings → Concise Views Counter → Data Export
   ```

3. Choose the **post type** you want to export:
   - **Post**
   - **Page**
   - Other custom post types (Pro only)

4. Click the **"Export CSV"** button. A `.csv` file will be automatically downloaded to your device.

---

## 📁 CSV File Structure

The exported file will contain the following columns:

| Post ID | Title          | Views   |
|---------|----------------|---------|
| 123     | Example Post    | 257     |
| 456     | Example Page    | 89      |

- **Post ID**: Unique ID of the post/page.
- **Title**: Title of the post/page.
- **Views**: Total number of views recorded.

**File naming format**:
```
page-views-export-{post_type}-YYYY-MM-DD_HH-MM-SS.csv
```

Example:
```
page-views-export-post-2025-07-11_12-00-00.csv
```

---

## 🆓 Lite vs Pro Feature Comparison

| Feature                             | Lite Version | Pro Version |
|-------------------------------------|--------------|-------------|
| Export post view data               | ✅ Available  | ✅ Available |
| Export page view data               | ✅ Available  | ✅ Available |
| Export custom post types            | 🔒 Disabled (Upgrade Required) | ✅ Available |
| Multi-post type export              | 🔒 Not available | ✅ Available (customizable) |
| Date-range filter for export        | 🔒 Not available | ✅ Available (extendable) |

> 🔒 Features marked as "Pro Only" are **visible but disabled** for Lite users, with upgrade prompts shown. We never hide locked features, ensuring transparency.

---

## ⚠️ Notes

- If no matching content is found for the selected post type, you will see a "No posts found" notice.
- The CSV uses **UTF-8 BOM encoding** to ensure compatibility with Excel and other spreadsheet tools.
- Export is only available to users with the `manage_options` capability (typically administrators).

---

## 🚀 How to Upgrade to Pro

To unlock custom post type export and additional advanced features, consider upgrading to **Concise Views Counter Pro**:

👉 [The purchase link will be provided here after the Pro version is released.](#)
---

## 🛠 Support

If you need assistance or run into issues, feel free to reach out:

- Plugin Page: [https://wordpress.org/plugins/concise-views-counter-pro](https://wordpress.org/plugins/concise-views-counter-pro)
- Email: `support@example.com`
