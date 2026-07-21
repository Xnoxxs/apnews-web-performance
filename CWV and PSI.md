# Baseline Performance Analysis

## Core Web Vitals

| Metric | Value | Status |
|--------|-------|--------|
| Largest Contentful Paint (LCP) | 3.6 s | Needs Improvement |
| Interaction to Next Paint (INP) | 155 ms | Good |
| Cumulative Layout Shift (CLS) | 0.03 | Good |

Core Web Vitals Assessment: Failed

## PageSpeed Insights Scores

| Category | Score |
|----------|------:|
| Performance | 31 |
| Accessibility | 79 |
| Best Practices | 54 |
| SEO | 85 |

## Lab Performance Metrics

| Metric | Value |
|--------|-------|
| First Contentful Paint (FCP) | 1.6 s |
| Largest Contentful Paint (LCP) | 5.1 s |
| Total Blocking Time (TBT) | 3,830 ms |
| Speed Index | 10.4 s |
| Cumulative Layout Shift (CLS) | 0.064 |

## Findings

### Finding 1: Very Large Network Payload

**Most likely cause:**

The homepage loads around 45 MB of resources, including large images, videos, advertisements, and third-party scripts.

**How does this affect users?**

The page takes longer to load because users must download a large amount of data. This is especially noticeable for users with slower internet connections or mobile data.

**Affected metrics:**

- Performance Score
- Largest Contentful Paint (LCP)
- Speed Index
- First Contentful Paint (FCP)

**Likely solution:**

Compress images, lazy-load media, reduce the number of third-party resources, and avoid downloading unnecessary content during the initial page load.

### Finding 2: High Total Blocking Time

**Most likely cause:**

The site loads many large JavaScript files and third-party scripts, resulting in long tasks that block the browser's main thread.

**How does this affect users?**

Even after the page appears, it may feel slow or unresponsive. Clicking buttons or links can take longer because the browser is still busy processing JavaScript.

**Affected metrics:**

- Total Blocking Time (TBT)
- Performance Score

**Likely solution:**

Reduce JavaScript size, split large scripts into smaller files, defer non-essential JavaScript, and remove unnecessary third-party code.

### Finding 3: Unoptimized Images

**Most likely cause:**

Many images are much larger than their displayed size and are not fully optimized or compressed.

**How does this affect users?**

Large images increase download time, causing pages to load more slowly and use more bandwidth.

**Affected metrics:**

- Largest Contentful Paint (LCP)
- First Contentful Paint (FCP)
- Speed Index

**Likely solution:**

Resize images to match their display size, use responsive images, and serve modern formats such as WebP or AVIF.

### Finding 4: Poor Cache Usage

**Most likely cause:**

Many static resources have short cache lifetimes or are not cached efficiently.

**How does this affect users?**

Returning visitors have to download many resources again instead of loading them from the browser cache, making repeat visits slower.

**Affected metrics:**

- Performance Score
- Largest Contentful Paint (LCP)
- First Contentful Paint (FCP)

**Likely solution:**

Increase cache lifetimes for static files using appropriate Cache-Control headers so browsers can reuse previously downloaded resources.

### Finding 5: Heavy Use of Third-Party Resources

**Most likely cause:**

A large number of third-party advertising, analytics, and tracking scripts are loaded when the page opens.

**How does this affect users?**

The page depends on many external services for advertisements, analytics, videos, and tracking. If these services are slow, the website becomes slower as well.

**Affected metrics:**

- Performance Score
- Largest Contentful Paint (LCP)
- Total Blocking Time (TBT)
- Speed Index

**Likely solution:**

Reduce unnecessary third-party services and delay loading non-essential scripts until after the main content has finished loading.
