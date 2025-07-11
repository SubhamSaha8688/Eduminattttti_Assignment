# Eduminattttti_Assignment
## 🔍 Objective
This audit evaluates the web performance of the following page:

**Target URL:** [https://www.edu123.in/category/boarding-schools-in-dehradun](https://www.edu123.in/category/boarding-schools-in-dehradun)  
**Search Keyword:** "Boarding Schools in Dehradun"

---

## 📊 Core Web Vitals Summary

Using Google's PageSpeed Insights and Chrome UX Report, key findings for both **mobile** and **desktop** are detailed below.

---

### 📱 Mobile Performance (Field Data)

![Mobile Core Web Vitals](./Mobile.png)

| Metric                         | Score   | Status     |
|-------------------------------|---------|------------|
| Largest Contentful Paint (LCP)| 3.3 s   | ❌ Needs improvement |
| Interaction to Next Paint (INP)| 202 ms | ✅ Good     |
| Cumulative Layout Shift (CLS) | 0.89    | ❌ High     |
| First Contentful Paint (FCP)  | 2.2 s   | ❌ Slightly slow |

⚠️ **Core Web Vitals Assessment: Failed**

---

### 📱 Mobile Performance (Lab Data)

![Mobile Lab Data](./Mobile_Performance.png)

| Metric                   | Score     |
|--------------------------|-----------|
| Performance Score        | 66        |
| First Contentful Paint   | 2.4 s     |
| Largest Contentful Paint | 7.4 s ❌   |
| Total Blocking Time      | 290 ms    |
| Cumulative Layout Shift  | 0.046 ✅   |
| Accessibility            | 86        |
| Best Practices           | 93        |
| SEO                      | 100 ✅     |

---

### 💻 Desktop Performance (Lab Data)

![Desktop Lab Data](./Desktop.png)

| Metric                   | Score     |
|--------------------------|-----------|
| Performance Score        | 92 ✅     |
| First Contentful Paint   | 0.8 s ✅  |
| Largest Contentful Paint | 0.8 s ✅  |
| Speed Index              | 1.4 s ✅  |
| Total Blocking Time      | 160 ms ✅ |
| CLS                      | 0.091 ✅  |

---

### 💻 Desktop Core Web Vitals

![Desktop Web Vitals](./Desktop_Performance.png)

| Metric                         | Score   | Status     |
|-------------------------------|---------|------------|
| Largest Contentful Paint (LCP)| 2.8 s   | ⚠️ Moderate |
| Interaction to Next Paint (INP)| 278 ms | ✅ Good     |
| Cumulative Layout Shift (CLS) | 0.86    | ❌ High     |
| First Contentful Paint (FCP)  | 1.5 s   | ✅ Good     |

⚠️ **Core Web Vitals Assessment: Failed**

---

## 📌 Observations & Bottlenecks

### 1. ❌ High Cumulative Layout Shift (CLS)
- **Cause:** Images or text loading without defined dimensions.
- **Solution:** Add fixed width/height to image containers and reserve space for dynamic content.

### 2. 🖼️ Large Unoptimized Images
- **Cause:** Multiple large PNG/JPEG assets.
- **Solution:** Convert to WebP, compress using TinyPNG/ImageOptim, and lazy-load below-the-fold images.

### 3. ⏱️ Slow Largest Contentful Paint (LCP)
- **Cause:** Late rendering of main banners or hero images.
- **Solution:** Inline critical CSS, preload fonts and hero image, and defer non-critical JavaScript.

### 4. ⚙️ Render-Blocking JavaScript/CSS
- **Cause:** Inline scripts or heavy third-party libraries.
- **Solution:** Split JS bundles, load non-essential scripts with `defer`/`async`.

---

## ✅ Recommended Technical Improvements

| Area                   | Recommendation                                                    |
|------------------------|-------------------------------------------------------------------|
| **Images**             | Use `loading="lazy"`, serve responsive images (`srcset`, WebP).   |
| **CSS/JS**             | Minify, bundle, and defer non-essential scripts.                  |
| **Fonts**              | Preload fonts and use `font-display: swap`.                       |
| **Server**             | Enable GZIP/Brotli, use HTTP/2, and a global CDN.                 |
| **Layout Shift**       | Set size attributes for all images and video placeholders.        |
| **Rendering Strategy** | Consider SSR (Server-Side Rendering) or static generation.        |

---

## 🧪 Tools Used

- Google PageSpeed Insights
- Chrome UX Report
- Lighthouse

---

## 📦 Conclusion

The Edu123 Dehradun listing page performs well on desktop but struggles significantly on mobile. Improving LCP and CLS on mobile should be the top priority. By applying modern performance best practices—especially around images, layout, and code optimization—the site can meet Core Web Vitals criteria and rank better in search results.
