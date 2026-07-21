# Stakeholders Audit

AP News demonstrates a strong technical foundation by using Server-Side Rendering (SSR), excellent search engine optimisation, and good accessibility practices. The website delivers news content immediately, even when JavaScript is disabled, providing a reliable experience for users and search engines.

Despite these strengths, overall performance is negatively affected by extensive JavaScript execution and numerous third-party advertising and analytics services. These significantly increase the amount of work performed by the browser before the page becomes fully interactive, particularly on lower-powered devices.

Several improvements can reduce loading time and improve responsiveness without requiring major architectural changes, while larger structural optimisations should be considered as longer-term investments.

## Overall Assessment

| Area | Assessment |
|------|------------|
| Business Risk | Medium |
| User Experience | Moderate |
| SEO Impact | Low |
| Reader Engagement Impact | Medium–High |
| Estimated Implementation Effort | Low–High (depends on recommendation) |

## What Is Working Well

### Strong Search Engine Optimisation

The website achieves an excellent SEO score and uses Server-Side Rendering to deliver complete HTML documents before JavaScript executes.

**Business value**

- Improves visibility in search engines.
- Increases opportunities for organic traffic.
- Ensures news articles are discoverable immediately after publication.

### Appropriate Rendering Strategy

The homepage continues to display meaningful content even when JavaScript is disabled, demonstrating that content is rendered on the server before client-side hydration.

**Business value**

- Faster access to news content.
- Reliable experience across different browsers and network conditions.
- Improved accessibility and crawlability.

### Good Accessibility

The website demonstrates good accessibility practices, making content available to a broader audience.

**Business value**

- Improves usability for a wider range of users.
- Supports compliance with accessibility expectations.
- Contributes to a better overall user experience.

## Highest Priority Opportunities

### 1. Reduce JavaScript Execution

**Business Impact**

Large amounts of JavaScript delay the time before users can fully interact with the website. This is particularly noticeable on slower devices and mobile networks, where extensive scripting increases waiting time before the page becomes fully responsive.

**Evidence**

- Approximately 3.1 seconds of JavaScript execution was recorded during page loading.
- Coverage analysis showed a significant amount of downloaded JavaScript was not used during the initial page load.

**Business Risk**

High

**Estimated Effort**

Medium

**Recommendation**

Reduce the initial JavaScript payload by improving code splitting, deferring non-essential functionality, and removing unnecessary JavaScript where possible.

### 2. Review Third-Party Services

**Business Impact**

Advertising, analytics, and other third-party services increase network activity and browser processing during page loading. While many provide important business functionality, they also contribute to slower page responsiveness.

**Evidence**

The performance recording identified substantial browser activity associated with multiple third-party services, including advertising and analytics platforms.

**Business Risk**

High

**Estimated Effort**

Low–Medium

**Recommendation**

Review third-party integrations to determine whether all services are necessary during the initial page load or whether some can be deferred until after the primary content has been displayed.

### 3. Improve Initial Resource Loading

**Business Impact**

The homepage downloads numerous resources before the page becomes fully interactive. Reducing unnecessary downloads can improve loading performance, particularly for first-time visitors.

**Evidence**

Coverage analysis identified unused CSS and JavaScript during the initial rendering process.

**Business Risk**

Medium

**Estimated Effort**

Medium

**Recommendation**

Continue reducing unused CSS and JavaScript while prioritising only the resources required for the initial page render.

### 4. Maintain Efficient Content Delivery

**Business Impact**

The website already benefits from CDN caching and Server-Side Rendering, which allow news content to reach users quickly. Maintaining this architecture while continuing to optimise server response times will help preserve a fast reading experience as traffic grows.

**Evidence**

Response headers show Cloudflare caching is used for the homepage, and request timing indicates a relatively fast server response before content is delivered.

**Business Risk**

Low

**Estimated Effort**

Low–Medium

**Recommendation**

Continue monitoring cache effectiveness and backend response times to ensure the current delivery strategy remains efficient during periods of high traffic.

## Priority Matrix

| Priority | Recommendation | Business Impact | Effort |
|----------|----------------|-----------------|--------|
| 1 | Reduce JavaScript execution | High | Medium |
| 2 | Review third-party services | High | Low–Medium |
| 3 | Reduce unused CSS and JavaScript | Medium | Medium |
| 4 | Continue optimising content delivery | Low–Medium | Low–Medium |

## Expected Business Benefits

Implementing these recommendations is expected to provide:

- Faster page loading and improved responsiveness.
- Better reader engagement through quicker interaction.
- Improved experience on slower devices and mobile networks.
- Reduced browser processing during page load.
- Preservation of strong SEO and accessibility performance while improving overall user experience.
