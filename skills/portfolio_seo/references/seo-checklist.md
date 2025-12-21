# SEO Checklist - Portfolio Website

## Technical SEO

### Meta Tags & Headers
- [ ] Unique `<title>` tag for each page (50-60 characters)
- [ ] Unique meta description (150-160 characters)
- [ ] Canonical URL tag present
- [ ] Language tag (`<html lang="pl">`)
- [ ] Viewport meta tag for mobile
- [ ] Charset declaration (UTF-8)

### Open Graph & Social Media
- [ ] og:title (social media title)
- [ ] og:description (social media description)
- [ ] og:image (1200x630px recommended)
- [ ] og:url (canonical URL)
- [ ] og:type (website, article, etc.)
- [ ] twitter:card (summary_large_image)
- [ ] twitter:title
- [ ] twitter:description
- [ ] twitter:image

### Structured Data (JSON-LD)
- [ ] Person/Organization schema on homepage
- [ ] BlogPosting schema on blog posts
- [ ] WebSite schema with search action
- [ ] BreadcrumbList schema where applicable
- [ ] FAQ schema (if applicable)
- [ ] Valid JSON-LD (test with Google Rich Results Test)

### Prerendering & Server-Side Rendering
- [ ] HTML content visible in "View Page Source"
- [ ] Not just empty `<div id="root"></div>`
- [ ] Full content available before JavaScript execution
- [ ] All critical content in initial HTML
- [ ] Dynamic routes prerendered (blog posts, projects)

### URL Structure
- [ ] Clean, readable URLs (no query parameters)
- [ ] Lowercase URLs
- [ ] Hyphens instead of underscores
- [ ] Logical hierarchy
- [ ] No duplicate URLs
- [ ] Proper URL canonicalization

### Sitemap & Robots
- [ ] sitemap.xml exists and is accessible
- [ ] Sitemap includes all important pages
- [ ] Sitemap submitted to Google Search Console
- [ ] robots.txt configured correctly
- [ ] No important pages blocked by robots.txt

### Internal Linking
- [ ] Logical link structure
- [ ] Related posts linked in blog articles
- [ ] Homepage links to main sections
- [ ] Footer contains important links
- [ ] Breadcrumbs implemented
- [ ] No broken internal links
- [ ] Descriptive anchor text (not "click here")

### External Links
- [ ] External links open in new tab (_blank)
- [ ] rel="noopener" for security on external links
- [ ] No broken external links

## Content SEO

### Headings
- [ ] Single H1 per page (main topic)
- [ ] Proper heading hierarchy (H1 → H2 → H3)
- [ ] Keywords in headings (naturally)
- [ ] Descriptive, not generic headings

### Content Quality
- [ ] Original, unique content (not duplicated)
- [ ] Valuable information for users
- [ ] Proper spelling and grammar
- [ ] Clear, readable writing style
- [ ] Content matches user intent
- [ ] Sufficient content length (500+ words for blog posts)
- [ ] Regular content updates

### Keywords
- [ ] Target keywords identified
- [ ] Keywords in title tags
- [ ] Keywords in meta descriptions
- [ ] Keywords in H1/H2 headings
- [ ] Keywords in first paragraph
- [ ] Natural keyword usage (not stuffing)
- [ ] Long-tail keyword variations

### Images
- [ ] All images have descriptive alt text
- [ ] Images optimized (WebP format preferred)
- [ ] Image file sizes reasonable (<200KB)
- [ ] Responsive images (srcset)
- [ ] Lazy loading for below-fold images
- [ ] Descriptive image filenames

### Blog-Specific
- [ ] Clear article topics
- [ ] Engaging titles
- [ ] Internal links to related posts
- [ ] Categories/tags implemented
- [ ] Publication dates visible
- [ ] Author attribution
- [ ] Reading time estimates
- [ ] Social share buttons

## Performance SEO

### Core Web Vitals
- [ ] **LCP (Largest Contentful Paint)** < 2.5s
- [ ] **FID (First Input Delay)** < 100ms
- [ ] **CLS (Cumulative Layout Shift)** < 0.1
- [ ] **FCP (First Contentful Paint)** < 1.8s
- [ ] **TTI (Time to Interactive)** < 3.5s

### Page Speed
- [ ] Mobile PageSpeed score > 90
- [ ] Desktop PageSpeed score > 90
- [ ] CSS minified
- [ ] JavaScript minified
- [ ] Gzip/Brotli compression enabled
- [ ] CDN configured
- [ ] Browser caching configured

### Bundle Optimization
- [ ] Code splitting implemented
- [ ] Tree shaking enabled
- [ ] Unused code removed
- [ ] Dependencies optimized
- [ ] Total bundle size < 300KB

### Font Loading
- [ ] font-display: swap for web fonts
- [ ] System fonts as fallback
- [ ] Fonts preloaded if critical
- [ ] Font subsetting (only needed characters)

## Mobile SEO

### Responsiveness
- [ ] Mobile-friendly design
- [ ] Passes Mobile-Friendly Test
- [ ] Touch targets 44x44px minimum
- [ ] Text readable without zooming
- [ ] No horizontal scrolling
- [ ] Content fits screen width

### Mobile Performance
- [ ] Fast load on 3G networks
- [ ] Mobile Core Web Vitals passing
- [ ] Reduced animations on mobile
- [ ] Optimized images for mobile

## Accessibility (A11y) - Impacts SEO

### WCAG 2.1 AA Compliance
- [ ] Keyboard navigation works
- [ ] Screen reader compatible
- [ ] Focus indicators visible
- [ ] Color contrast ratios meet standards (4.5:1)
- [ ] Skip navigation links
- [ ] ARIA labels where needed
- [ ] Form labels properly associated
- [ ] Error messages accessible

## Security & Trust

### HTTPS & Security
- [ ] HTTPS enabled (SSL certificate)
- [ ] No mixed content warnings
- [ ] Security headers configured
- [ ] No insecure forms

### Privacy & Legal
- [ ] Privacy policy accessible
- [ ] Cookie policy if applicable
- [ ] Terms of service
- [ ] GDPR/RODO compliance
- [ ] Contact information visible

## Monitoring & Analytics

### Search Console
- [ ] Google Search Console configured
- [ ] Bing Webmaster Tools configured
- [ ] No crawl errors
- [ ] Index coverage healthy
- [ ] Mobile usability issues resolved

### Analytics
- [ ] Google Analytics or alternative installed
- [ ] Conversion tracking set up
- [ ] Events tracked (clicks, form submissions)
- [ ] Traffic sources monitored

### Regular Monitoring
- [ ] Weekly traffic analysis
- [ ] Monthly position tracking
- [ ] Quarterly content audits
- [ ] Regular technical SEO audits
