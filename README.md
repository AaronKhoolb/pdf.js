# PDF.js with Cross‑Domain Support (v5.3.31)

## 📖 Description

A fork of [Mozilla PDF.js](https://github.com/mozilla/pdf.js) v5.3.31 with origin‑check bypass. You can now load and view any PDF from remote domains directly via:

```
https://<your-domain>/web/viewer.html?file=<PDF_URL>
```

Functionality remains fully compatible with upstream PDF.js; the only enhancement is seamless cross‑domain integration.

## ✨ Features

- **Cross‑Domain Loading**: Removes the default “file origin does not match viewer” block.

- **No Core Changes**: `/pdf.mjs` and core renderer are untouched for compatibility.

- **Alist Preview**: Easily integrate in Alist by updating **Manage → Settings → Preview → Iframe previews**:

  ```json
  "pdf": {
    "PDF.js": "https://<your-domain>/web/viewer.html?file=$e_url"
  }
  ```

- **Direct Demo**:

  - [PDF link](https://aaronkhoolb.github.io/pdf.js/web/viewer.html?file=https%3A%2F%2Fdrive.khoolb.com%2Fp%2F%25E5%2585%25AC%25E5%25BC%2580%25E9%25A1%25B5%25E9%259D%25A2%2FMisc%2Fpdfjs.pdf%3Fsign%3DCF6D10OdBqD2ln-XgliNnRw0ARoHR6IakyepIYD6-cA%3D%3A0)
  - [Alist demo](https://drive.khoolb.com/Misc/pdfjs.pdf)

## 🚀 Installation & Usage

### 1. GitHub Pages Deployment

1. **Fork** this repository.

2. Go to **Settings → Pages**, select branch `main`, and click **Save**.

3. Wait for GitHub Actions to finish deployment.

4. Access:

   ```
   https://<YOUR_GITHUB_USERNAME>.github.io/pdf.js/web/viewer.html?file=<PDF_URL>
   ```

### 2. 宝塔/BT Panel Deployment

1. In BT panel, go to **Websites → Add Site** and create a new **PHP Project**, pointing the document root to your domain’s directory.

2. Navigate to **Files → Site Directory**, click the **URL** button at the top, and choose **Install from Repository**:

   - Repository URL:

     ```
     https://github.com/AaronKhoolb/pdf.js/archive/refs/heads/main.zip
     ```

   - Click **Download and Extract**, then wait for completion.

3. Once extracted, copy all files from the `pdf.js-main` folder into your site’s root directory (e.g., `/www/wwwroot/<your-domain>/`).

4. Edit the Nginx MIME types configuration:

   ```
   /www/server/nginx/conf/mime.types
   ```

   Locate the line:

   ```
   application/javascript  js;
   ```

   and modify it to:

   ```
   application/javascript  js mjs;
   ```

5. Reload Nginx or restart the site service. Then access in your browser:

   ```
   https://<your-domain>/web/viewer.html?file=<PDF_URL>
   ```

## 📜 License

This project is based on [Mozilla PDF.js](https://github.com/mozilla/pdf.js), licensed under the [Apache License 2.0](https://www.apache.org/licenses/LICENSE-2.0).

## 👥 Contributors

[<img src="https://khoolb.com/images/favicon_180x180.jpg" alt="Khoo lb" style="zoom:40%;" />](https://khoolb.com/)
[<img src="https://www.dkly.top/image/e6d8e7b607d3ac82a4894570997d152a.png" alt="Davon" style="zoom:40%;" />](https://www.dkly.top/)



*Thank you to all who contributed!*
