## frontend-only-web-application  
### Easy Buying – A Modern Frontend for a Fruit & Vegetable Stall 🥕🍎

> A lightweight, responsive frontend-only website for an imaginary stall called **Easy Buying**, built with **HTML**, **CSS**, and **JavaScript**.  
> Created by **Francis Remoshan** as a first-year project.

---

### Visuals

> _Hero / Screenshot Placeholder_  
> Replace the path below with your own image once available:

```md
![Easy Buying – Homepage Preview](docs/images/hero-easy-buying.png)
```

---

### Features ✨

- ✅ **Responsive Layout** – Optimized for desktops, tablets, and mobile devices.
- 🧺 **Product Showcase** – Clean listing of fruits and vegetables with prices and descriptions.
- 🔎 **Search & Filter** – Quickly find items by name or category.
- 🛒 **Lightweight “Cart-like” Experience** – Add items to a pseudo-cart (frontend-only; no backend).
- 🎨 **Modern UI/UX** – Minimalist design using pure CSS, focusing on readability and usability.
- ⚡ **Vanilla JS Only** – No frameworks, easy to understand and extend.
- 🌐 **Configurable Endpoints** – Optional environment-based configuration for APIs (if you connect one later).

---

### Getting Started 🚀

#### Prerequisites

You only need a modern web browser.  
For local development with a simple server, you can use any of the following options:

- **Node.js** (optional, for running a static server)
- Or a simple Live Server extension in your editor

#### Installation

Clone the repository and open the project:

```bash
# Clone the repository
git clone https://github.com/FrancisRemoshan/frontend-only-web-application.git

# Move into the project directory
cd frontend-only-web-application
```

Run with a simple static server (optional but recommended):

```bash
# Example using Node's npx (if you have Node installed)
npx serve .

# or using Python 3
python -m http.server 3000

# Then open in your browser:
# http://localhost:3000
```

Or simply open `index.html` directly in your browser (double-click or drag-and-drop into a browser window).

---

### Usage 📦

Below is an example of how a typical product card and basic interaction might work in this project.

**HTML:**

```html
<!-- Product card -->
<div class="product-card" data-product-id="apple-001">
  <h3 class="product-name">Fresh Red Apples</h3>
  <p class="product-price">$2.50 / kg</p>
  <button class="btn-add-to-cart">Add to Basket</button>
</div>

<!-- Basket summary -->
<div id="basket-summary">
  <span id="basket-count">0</span> items in your basket
</div>

<script src="js/app.js"></script>
```

**JavaScript (`js/app.js`):**

```js
document.addEventListener("DOMContentLoaded", () => {
  const basketCountEl = document.getElementById("basket-count");
  const addButtons = document.querySelectorAll(".btn-add-to-cart");

  let basketCount = 0;

  addButtons.forEach((btn) => {
    btn.addEventListener("click", () => {
      basketCount += 1;
      basketCountEl.textContent = basketCount.toString();
    });
  });
});
```

Open the site in your browser and click **Add to Basket** on any product to see the basket count update in real time.

---

### Configuration ⚙️

While this is a **frontend-only** application, you can optionally configure environment-like variables (e.g., API endpoints) using a simple config file (such as `config.js`) or build-time environment injection.

| Variable Name         | Description                                      | Default Value                   | Required |
|-----------------------|--------------------------------------------------|---------------------------------|----------|
| `VITE_API_BASE_URL`   | Base URL of a backend API (if you add one)      | `""` (no backend / static only) | No       |
| `VITE_IMAGE_BASE_URL` | Base path or CDN for product images             | `"/assets/images"`              | No       |
| `VITE_ENVIRONMENT`    | Environment label (`development`, `production`) | `"development"`                 | No       |

**Example `config.js` (if you choose to use one):**

```js
window.EASY_BUYING_CONFIG = {
  apiBaseUrl: "", // e.g. "https://api.example.com"
  imageBaseUrl: "/assets/images",
  environment: "development",
};
```

---

### Contributing 🤝

Contributions are welcome! To propose changes:

1. **Fork** the repository to your GitHub account.
2. **Create a feature branch**:

   ```bash
   git checkout -b feature/your-feature-name
   ```

3. **Make your changes** (code, tests, documentation).
4. **Commit** with a clear message:

   ```bash
   git commit -m "Add: short description of your change"
   ```

5. **Push** your branch:

   ```bash
   git push origin feature/your-feature-name
   ```

6. **Open a Pull Request** against the `main` branch:
   - Describe the motivation, changes, and any relevant screenshots.
   - Reference any related issues if applicable.

Please keep your changes focused and small where possible for easier review.

---

### License 📄

This project is licensed under the **MIT License**.

```md
MIT License

Copyright (c) 2026 Francis Remoshan

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```