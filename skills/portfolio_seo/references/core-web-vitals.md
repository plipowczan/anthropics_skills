# Core Web Vitals Analysis Guide

## Overview

Core Web Vitals are Google's standardized metrics for measuring user experience quality on websites. They directly impact SEO rankings and are critical for portfolio websites.

## The Three Core Web Vitals

### 1. Largest Contentful Paint (LCP)

**What it measures:** Loading performance - time until the largest content element becomes visible

**Targets:**
- **Good:** < 2.5 seconds
- **Needs Improvement:** 2.5 - 4.0 seconds
- **Poor:** > 4.0 seconds

**Common causes of poor LCP:**
- Large unoptimized images
- Slow server response time (TTFB)
- Render-blocking JavaScript/CSS
- Client-side rendering without prerendering

**How to improve LCP:**
1. **Optimize images:**
   - Convert to WebP format
   - Implement responsive images (srcset)
   - Lazy load below-fold images
   - Compress images (<200KB target)
   - Use CDN for image delivery

2. **Implement prerendering:**
   - Static site generation (SSG)
   - Server-side rendering (SSR)
   - Pre-render critical pages at build time

3. **Optimize fonts:**
   - Use `font-display: swap`
   - Preload critical fonts
   - Use system fonts as fallback
   - Consider variable fonts

4. **Minimize JavaScript:**
   - Code splitting (React.lazy())
   - Tree shaking
   - Remove unused dependencies
   - Defer non-critical JS

5. **Reduce server response time:**
   - Use CDN (Vercel Edge Network)
   - Enable caching
   - Optimize backend queries

### 2. First Input Delay (FID) / Interaction to Next Paint (INP)

**What it measures:** Interactivity - time between user's first interaction and browser response

**Note:** FID is being replaced by INP (Interaction to Next Paint) in March 2024

**Targets (FID):**
- **Good:** < 100 milliseconds
- **Needs Improvement:** 100 - 300 milliseconds
- **Poor:** > 300 milliseconds

**Targets (INP):**
- **Good:** < 200 milliseconds
- **Needs Improvement:** 200 - 500 milliseconds
- **Poor:** > 500 milliseconds

**Common causes of poor FID/INP:**
- Long JavaScript execution
- Heavy main thread tasks
- Large JavaScript bundles
- Unoptimized event handlers

**How to improve FID/INP:**
1. **Break up long tasks:**
   - Split code into smaller chunks
   - Use Web Workers for heavy computations
   - Defer non-essential JavaScript

2. **Optimize JavaScript execution:**
   - Remove unused JavaScript
   - Minimize third-party scripts
   - Use code splitting
   - Implement lazy loading

3. **Optimize event handlers:**
   - Debounce scroll/resize listeners
   - Use passive event listeners
   - Avoid expensive calculations in handlers

4. **Reduce Total Blocking Time (TBT):**
   - TBT < 200ms for good score
   - Measure with Lighthouse
   - Optimize render-blocking resources

### 3. Cumulative Layout Shift (CLS)

**What it measures:** Visual stability - unexpected layout shifts during page load

**Targets:**
- **Good:** < 0.1
- **Needs Improvement:** 0.1 - 0.25
- **Poor:** > 0.25

**Common causes of layout shift:**
- Images without dimensions
- Ads/embeds without reserved space
- Dynamically injected content
- Web fonts causing FOIT/FOUT
- Animations that trigger layout

**How to improve CLS:**
1. **Reserve space for images:**
   ```html
   <!-- Always include width and height -->
   <img src="image.jpg" width="800" height="600" alt="Description" />

   <!-- Or use aspect-ratio CSS -->
   <img src="image.jpg" style="aspect-ratio: 16/9; width: 100%;" />
   ```

2. **Reserve space for ads/embeds:**
   ```css
   .ad-container {
     min-height: 250px; /* Reserve space before ad loads */
   }
   ```

3. **Optimize font loading:**
   ```html
   <!-- Use font-display: swap -->
   <link rel="preconnect" href="https://fonts.googleapis.com">
   <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700&display=swap" rel="stylesheet">
   ```

4. **Avoid inserting content above existing content:**
   - Load content below the fold
   - Use `transform` for animations (not `top/left`)
   - Avoid injecting content dynamically

5. **Preload critical resources:**
   ```html
   <link rel="preload" as="font" href="/fonts/inter.woff2" crossorigin>
   ```

## Additional Important Metrics

### First Contentful Paint (FCP)

**What it measures:** Time until first text/image appears

**Targets:**
- **Good:** < 1.8 seconds
- **Needs Improvement:** 1.8 - 3.0 seconds
- **Poor:** > 3.0 seconds

**Optimization strategies:**
- Inline critical CSS
- Preconnect to required origins
- Minimize render-blocking resources
- Use prerendering/SSR

### Time to Interactive (TTI)

**What it measures:** Time until page is fully interactive

**Targets:**
- **Good:** < 3.5 seconds
- **Needs Improvement:** 3.5 - 7.3 seconds
- **Poor:** > 7.3 seconds

**Optimization strategies:**
- Reduce JavaScript execution time
- Minimize main thread work
- Code splitting
- Defer non-critical JavaScript

### Speed Index

**What it measures:** How quickly content is visually displayed

**Targets:**
- **Good:** < 3.4 seconds
- **Needs Improvement:** 3.4 - 5.8 seconds
- **Poor:** > 5.8 seconds

**Optimization strategies:**
- Optimize above-the-fold content
- Lazy load below-fold images
- Minimize render-blocking resources

### Total Blocking Time (TBT)

**What it measures:** Total time page is blocked from responding to user input

**Targets:**
- **Good:** < 200 milliseconds
- **Needs Improvement:** 200 - 600 milliseconds
- **Poor:** > 600 milliseconds

**Optimization strategies:**
- Break up long tasks
- Optimize third-party code
- Reduce JavaScript execution time

## Performance Analysis Workflow

### Step 1: Measure Current Performance

**Tools:**
1. **Lighthouse (Chrome DevTools):**
   - Open DevTools (F12)
   - Go to Lighthouse tab
   - Select "Performance" + "SEO"
   - Run audit

2. **PageSpeed Insights:**
   - Visit: https://pagespeed.web.dev/
   - Enter URL
   - Analyze both Mobile and Desktop

3. **Chrome UX Report (CrUX):**
   - Real user data from Chrome users
   - Available in PageSpeed Insights
   - Shows field data (real users) vs lab data (Lighthouse)

4. **Vercel Speed Insights:**
   - Real user monitoring
   - Core Web Vitals tracking
   - Integrated analytics

### Step 2: Identify Issues

**Lighthouse Issues to Look For:**

**LCP Issues:**
- Large images blocking LCP
- Slow server response time
- Render-blocking resources
- Inefficient cache policy

**FID/INP Issues:**
- Long JavaScript tasks
- Third-party scripts
- Main thread blocking

**CLS Issues:**
- Images without dimensions
- Layout shifts from fonts
- Dynamic content injection

**General Issues:**
- Large bundle sizes
- Unoptimized images
- Render-blocking CSS/JS
- No text compression

### Step 3: Prioritize Fixes

**Priority Matrix:**

**High Impact, Low Effort (Do First):**
- Add width/height to images (fixes CLS)
- Enable text compression
- Use font-display: swap
- Lazy load below-fold images
- Minify CSS/JS

**High Impact, Medium Effort (Do Next):**
- Implement code splitting
- Convert images to WebP
- Prerender critical pages
- Optimize fonts
- Remove unused CSS/JS

**High Impact, High Effort (Plan Carefully):**
- Implement SSR/SSG
- Redesign architecture
- Replace heavy dependencies
- Complete performance overhaul

**Low Priority:**
- Minor optimizations (<5% improvement)
- Edge case fixes
- Diminishing returns optimizations

## Portfolio-Specific Optimizations

### Current Issues (Based on Project Context)

**From SRS.md - Known Performance Issues:**

| Metric | Current | Target | Status |
|--------|---------|--------|--------|
| FCP | 5.3s | < 1.8s | ❌ Critical |
| LCP | 5.8s | < 2.5s | ❌ Critical |
| TBT | 78ms | < 200ms | ✅ Good |
| CLS | 0 | < 0.1 | ✅ Good |
| TTI | 5.8s | < 3.5s | ⚠️ Needs work |
| Speed Index | 5.5s | < 3.0s | ⚠️ Needs work |

**Bundle Size:**
- Current JS: 483.84 KB (gzip: 155.43 KB)
- Target: < 300 KB
- CSS: 26.86 KB (gzip: 4.97 KB) ✅

### Recommended Fixes for Portfolio

**Priority 1 (Critical - Immediate Action):**

1. **Font Loading Optimization:**
   ```html
   <!-- Add display=swap to Google Fonts URL -->
   <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700&display=swap" rel="stylesheet">

   <!-- Or use font-display in @font-face -->
   @font-face {
     font-family: 'Inter';
     font-display: swap;
     src: url('/fonts/inter.woff2') format('woff2');
   }
   ```

2. **Code Splitting with React.lazy():**
   ```javascript
   // Instead of direct imports
   import BlogPostPage from './pages/BlogPostPage';

   // Use lazy loading
   const BlogPostPage = React.lazy(() => import('./pages/BlogPostPage'));
   const ProjectPage = React.lazy(() => import('./pages/ProjectPage'));

   // Wrap routes with Suspense
   <Suspense fallback={<LoadingSpinner />}>
     <Routes>
       <Route path="/blog/:slug" element={<BlogPostPage />} />
       <Route path="/projects/:slug" element={<ProjectPage />} />
     </Routes>
   </Suspense>
   ```

3. **Image Optimization:**
   ```bash
   # Convert images to WebP
   npm run img:convert

   # Add width/height attributes
   <img src="project.webp" width="800" height="600" alt="Project" loading="lazy" />
   ```

**Priority 2 (High - Next Sprint):**

4. **Tree Shaking & Bundle Analysis:**
   ```bash
   # Analyze bundle
   npm run build -- --mode=analyze

   # Look for:
   # - Unused dependencies
   # - Duplicate code
   # - Large libraries that could be replaced
   ```

5. **Preconnect to External Resources:**
   ```html
   <link rel="preconnect" href="https://fonts.googleapis.com">
   <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
   ```

6. **Defer Non-Critical JavaScript:**
   ```javascript
   // Analytics, non-critical features
   const Analytics = React.lazy(() => import('./components/Analytics'));
   ```

**Priority 3 (Medium - Future Optimization):**

7. **Service Worker for Caching:**
   ```javascript
   // Implement offline support + faster loads
   // Can use Workbox or custom service worker
   ```

8. **Resource Hints:**
   ```html
   <link rel="dns-prefetch" href="https://vercel.com">
   <link rel="prefetch" href="/blog">
   ```

## Testing & Verification

### Local Testing

```bash
# Build production bundle
npm run build:prerender

# Analyze bundle size
npm run preview

# Test with Lighthouse
# DevTools → Lighthouse → Run audit
```

### Continuous Monitoring

**Set up monitoring:**
1. **Vercel Speed Insights** (already installed)
2. **Google Search Console** - Performance reports
3. **PageSpeed Insights** - Weekly checks

**Create alerts:**
- LCP > 3.0s → Alert
- FID > 150ms → Alert
- CLS > 0.15 → Alert

### A/B Testing

Test performance improvements:
1. Measure baseline (before)
2. Implement optimization
3. Measure results (after)
4. Compare metrics
5. Keep if >10% improvement

## Quick Wins Checklist

Easy optimizations with high impact:

- [ ] Add `font-display: swap` to all web fonts
- [ ] Add width/height to all images
- [ ] Lazy load below-fold images
- [ ] Minify CSS and JavaScript (Vite does this)
- [ ] Enable text compression (Vercel does this)
- [ ] Add `loading="lazy"` to images
- [ ] Implement code splitting for routes
- [ ] Preconnect to external domains
- [ ] Remove unused CSS/JS
- [ ] Optimize images to WebP
- [ ] Set proper cache headers (Vercel does this)
- [ ] Use CDN (Vercel provides this)

## Common Mistakes to Avoid

❌ **Don't:**
- Optimize without measuring first
- Focus only on Lighthouse score
- Ignore real user metrics (CrUX)
- Over-optimize (diminishing returns)
- Break functionality for performance
- Ignore mobile performance

✅ **Do:**
- Measure before and after
- Test on real devices
- Monitor continuously
- Prioritize high-impact fixes
- Balance performance and UX
- Test on slow networks (3G)

## Resources

- [Web.dev Core Web Vitals](https://web.dev/vitals/)
- [Google PageSpeed Insights](https://pagespeed.web.dev/)
- [Lighthouse Documentation](https://developers.google.com/web/tools/lighthouse)
- [Chrome UX Report](https://developers.google.com/web/tools/chrome-user-experience-report)
- [Vercel Speed Insights](https://vercel.com/docs/concepts/analytics)
