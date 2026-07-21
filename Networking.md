# Networking

## Hard Reload

| Metric | Value |
|--------|-------|
| Requests | 736 |
| Data transferred | 9.9 MB |
| Total resource size | 36.6 MB |
| Finish time | 7.13 s |
| DOMContentLoaded | 2.52 s |

## Compression Reduction

- Transferred: 9.9 MB
- Total resources: 36.6 MB

This means approximately 26.7 MB of data was saved through compression, a reduction of about 73%.

## Soft Reload

| Metric | Value |
|--------|-------|
| Requests | 679 |
| Data transferred | 1.0 MB |
| Total resource size | 36.4 MB |
| Finish time | 6.60 s |
| DOMContentLoaded | 2.97 s |
| Load | 6.21 s |

## Reduction Due to Caching

- Hard reload transferred: 9.9 MB
- Soft reload transferred: 1.0 MB

The browser downloaded approximately 8.9 MB less data on the second visit, which is roughly a 90% reduction due to caching.

## Resource Breakdown

| Resource Type | Transferred | Resource Size |
|---------------|-------------|---------------|
| JavaScript | 89.1 kB | 3.42 MB |
| Images | 640 kB | 21.9 MB |
| CSS | 0.0 kB | 2.13 MB |

The transferred sizes are much smaller than the total resource sizes:

- JavaScript: 89.1 kB transferred vs 3.42 MB resources
- Images: 640 kB transferred vs 21.9 MB resources
- CSS: 0 kB transferred vs 2.13 MB resources (served entirely from cache)

This indicates that compression and browser caching are both being used effectively.

## Findings

### Finding 1: Very Large Number of Requests

**Most likely cause:**

The homepage loads many news articles, advertisements, analytics scripts, videos, fonts, and other third-party resources.

**How does this affect users?**

Making 736 network requests increases the amount of work the browser has to perform before the page is fully loaded. This can slow down loading, especially on slower devices and networks.

**Affected metrics:**

- Finish Time
- Performance
- Largest Contentful Paint (LCP)

**Likely solution:**

Reduce unnecessary requests by combining files where possible, removing unused third-party scripts, and lazy-loading resources that are not immediately needed.

### Finding 2: Images Make Up Most of the Page Size

**Most likely cause:**

The homepage contains many high-resolution news photographs.

**How does this affect users?**

Images account for approximately 22 MB of the 36.6 MB total page size, meaning they are responsible for most of the download. Large images increase loading times and consume more mobile data.

**Affected metrics:**

- Largest Contentful Paint (LCP)
- Speed Index
- Finish Time

**Likely solution:**

Use responsive images, compress images further, and serve modern formats such as WebP or AVIF where possible.

### Finding 3: JavaScript Is Still Significant

**Most likely cause:**

The website loads numerous JavaScript files for advertisements, analytics, videos, comments, and interactive features.

**How does this affect users?**

Although JavaScript is much smaller than images, over 3.4 MB of scripts still need to be processed, increasing CPU usage and slowing page interaction.

**Affected metrics:**

- Total Blocking Time (TBT)
- Interaction to Next Paint (INP)
- Performance Score

**Likely solution:**

Remove unused JavaScript, split large bundles into smaller files, and defer scripts that are not required during the initial page load.

### Finding 4: Browser Caching Works Very Well

**Most likely cause:**

Static resources such as JavaScript, CSS, images, and fonts are cached by the browser after the first visit.

**How does this affect users?**

The amount of downloaded data drops from 9.9 MB to 1.0 MB on a normal refresh, making repeat visits much faster and reducing bandwidth usage.

**Affected metrics:**

- Data Transferred
- Finish Time
- Overall Performance

**Likely solution:**

Continue using long cache lifetimes for static resources and ensure new versions are delivered using cache-busting filenames when files change.
