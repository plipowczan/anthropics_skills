---
name: portfolio_seo
description: Kompleksowa analiza SEO i optymalizacja dla projektu portfolio Pawla Lipowczana. Uzyj do analizy obecnego stanu SEO strony, audytu technicznego, sprawdzenia Core Web Vitals, weryfikacji structured data, oraz przygotowania planu optymalizacji. Obejmuje optymalizacje dla tradycyjnych wyszukiwarek (Google, Bing) oraz dla wyszukiwan w modelach jezykowych (ChatGPT Search, Perplexity, Claude). Specjalizuje sie w analizie React SPA z prerenderingiem, Vercel deployment, oraz optymalizacji wydajnosci. Wzorowany na dokumentacji projektu (PRD.md, SRS.md) oraz istniejacych plikach SEO (PRERENDERING.md, SEO_VERIFICATION.md).
license: Apache-2.0
---

# Portfolio SEO Analysis & Optimization

Kompleksowy skill do analizy SEO i optymalizacji projektu portfolio. Obejmuje audyt techniczny, analiz\u0119 tre\u015bci, Core Web Vitals, oraz optymalizacj\u0119 dla wyszukiwarek AI (LLM optimization).

## Quick Reference

### Kiedy u\u017cy\u0107 tego skila

- Analiza obecnego stanu SEO strony portfolio
- Audyt techniczny (meta tagi, structured data, prerendering)
- Analiza wydajno\u015bci (Core Web Vitals, bundle size)
- Przygotowanie planu optymalizacji SEO
- Optymalizacja tre\u015bci dla LLM (ChatGPT, Perplexity, Claude)
- Weryfikacja po wdro\u017ceniu zmian SEO
- Por\u00f3wnanie z best practices dla portfolio developers

### Kontekst projektu

**Stack technologiczny:**
- React 19.2.0 + Vite 7.2.2
- Tailwind CSS 3.4.18 + Framer Motion 12.23.24
- React Router 7.9.6 (client-side routing)
- Prerendering: Puppeteer Core 24.32.1 + @sparticuz/chromium
- Deployment: Vercel (Edge Network, CDN)

**Architektura:**
- Single Page Application (SPA) z build-time prerenderingiem
- Statyczne HTML dla ka\u017cdej strony (SEO)
- Client-side routing po hydration
- Markdown-based blog system
- Brak backendu (fully static)

**Dokumentacja projektu:**
- `docs/portfolio/SRS.md` - Specyfikacja techniczna
- `docs/portfolio/PRD.md` - Wymagania produktowe
- `docs/portfolio/seo/PRERENDERING.md` - Dokumentacja prerenderingu
- `docs/portfolio/seo/SEO_VERIFICATION.md` - Checklist weryfikacji

## Workflow: SEO Analysis & Optimization

Follow these steps in order for comprehensive SEO analysis:

### Step 1: Initial Assessment

Gather information about current state:

1. **Read project documentation:**
   - `docs/portfolio/SRS.md` (technical specs, known issues)
   - `docs/portfolio/PRD.md` (business requirements)
   - `docs/portfolio/seo/PRERENDERING.md` (prerendering details)
   - `docs/portfolio/seo/SEO_VERIFICATION.md` (verification checklist)

2. **Check current SEO status from SRS.md:**
   - Current Core Web Vitals (FCP, LCP, TBT, CLS, TTI)
   - Bundle sizes (JS, CSS)
   - Known issues and TODOs
   - Implemented features (prerendering, structured data, etc.)

3. **Identify user's primary concern:**
   - Ask: "What specific SEO area would you like to focus on?"
     - Technical SEO (meta tags, structured data)
     - Performance (Core Web Vitals)
     - Content optimization
     - LLM optimization (AI search)
     - Competitive analysis
     - Full audit (all areas)

### Step 2: Technical SEO Audit

**Reference file:** [seo-checklist.md](references/seo-checklist.md)

Perform comprehensive technical audit:

1. **Meta Tags & Headers:**
   - Check all pages for unique titles (<60 chars)
   - Verify meta descriptions (150-160 chars)
   - Confirm canonical URLs
   - Check Open Graph tags
   - Verify Twitter Card tags

2. **Structured Data:**
   - Inspect JSON-LD schemas on all pages
   - Validate with Google Rich Results Test
   - Check for Person, Article, WebSite schemas
   - Verify breadcrumbs implementation

3. **Prerendering Verification:**
   - View Page Source on deployed site
   - Confirm full HTML content (not empty div)
   - Check if dynamic routes (blog posts) are prerendered
   - Verify `/blog/:slug` pages have static HTML

4. **URL Structure & Navigation:**
   - Check for clean URLs (no query params)
   - Verify sitemap.xml exists and is updated
   - Check robots.txt configuration
   - Test internal linking structure

5. **Images & Media:**
   - Verify all images have alt text
   - Check image optimization (WebP, sizes)
   - Confirm lazy loading implementation
   - Test responsive images

**Output:** Generate Technical SEO Report with findings and priority fixes.

### Step 3: Performance Analysis

**Reference file:** [core-web-vitals.md](references/core-web-vitals.md)

Analyze Core Web Vitals and performance metrics:

1. **Compare against SRS.md baseline:**
   - Current metrics from SRS.md:
     - FCP: 5.3s (target < 1.8s) ❌
     - LCP: 5.8s (target < 2.5s) ❌
     - TBT: 78ms (target < 200ms) ✅
     - CLS: 0 (target < 0.1) ✅
     - TTI: 5.8s (target < 3.5s) ⚠️

2. **Identify performance bottlenecks:**
   - Font loading (likely culprit for FCP/LCP)
   - Bundle size (483.84 KB, target < 300 KB)
   - Code splitting implementation
   - Image optimization
   - Third-party scripts

3. **Calculate performance impact:**
   - Prioritize fixes by impact (High/Medium/Low)
   - Estimate improvement potential
   - Consider implementation effort

4. **Generate actionable recommendations:**
   - Priority 1: Quick wins (font-display: swap, image optimization)
   - Priority 2: Medium effort (code splitting, WebP conversion)
   - Priority 3: Long-term (architecture changes)

**Output:** Performance Analysis Report with prioritized optimization plan.

### Step 4: Content Optimization for Traditional SEO

**Reference file:** [seo-checklist.md](references/seo-checklist.md) (Content SEO section)

Analyze content quality and optimization:

1. **Homepage (/):**
   - Hero section: Clear value proposition?
   - About section: Keyword-rich, factual?
   - Projects: Descriptive titles and descriptions?
   - Skills: Properly categorized and described?
   - Contact: Complete information?

2. **Blog Posts (/blog/:slug):**
   - Title optimization (keywords, < 60 chars)
   - Meta descriptions (unique, compelling)
   - Content structure (H1 → H2 → H3)
   - Internal linking (related posts)
   - Reading time and dates visible
   - Categories/tags implemented

3. **Legal Pages:**
   - Privacy Policy complete and accessible
   - Terms of Service clear
   - Cookie Policy if applicable
   - Footer links to all legal pages

4. **Content Quality:**
   - Original, valuable content
   - Proper grammar and spelling
   - Sufficient content length (blog: 500+ words)
   - Regular updates and fresh content

**Output:** Content Optimization Report with specific improvements.

### Step 5: LLM Optimization Analysis

**Reference file:** [llm-optimization.md](references/llm-optimization.md)

Optimize for AI-powered search (ChatGPT, Perplexity, Claude):

1. **Semantic HTML Structure:**
   - Check for proper semantic tags (article, section, header, etc.)
   - Verify heading hierarchy
   - Confirm use of `<time>` tags for dates
   - Check metadata completeness (author, publish date)

2. **Direct Answer Optimization:**
   - Homepage: Clear "Who/What/Where" statements
   - About section: Explicit credentials and expertise
   - Blog posts: TL;DR or summary in first paragraph
   - Projects: Clear problem/solution format

3. **Structured Data for LLMs:**
   - Person schema with comprehensive details
   - Article schema with keywords and categories
   - FAQ schema where applicable
   - Breadcrumb schema for navigation context

4. **Content Format for Citations:**
   - Clear attribution (author, date)
   - Factual, specific claims (with numbers)
   - Explicit relationships (related articles)
   - Technical terms defined
   - Temporal context (dates, versions)

5. **Test LLM Understanding:**
   - Ask ChatGPT: "Who is Pawel Lipowczan?"
   - Check Perplexity citations
   - Verify information accuracy in AI responses

**Output:** LLM Optimization Report with recommendations for AI search visibility.

### Step 6: Competitive Analysis (Optional)

Compare portfolio against industry best practices:

1. **Identify competitors:**
   - Other portfolio sites of developers
   - Industry leaders in same tech stack
   - Top-ranking developer portfolios

2. **Analyze competitor SEO:**
   - Lighthouse scores comparison
   - Core Web Vitals comparison
   - Content structure and quality
   - Backlink profiles
   - Structured data implementation

3. **Identify gaps and opportunities:**
   - What are competitors doing better?
   - What unique advantages does portfolio have?
   - Untapped SEO opportunities

**Output:** Competitive Analysis Report with strategic recommendations.

### Step 7: Generate Comprehensive SEO Plan

Consolidate all findings into actionable plan:

**Plan Structure:**

```markdown
# SEO Optimization Plan - Portfolio

## Executive Summary
- Current SEO score: X/100
- Main issues: [List 3-5 critical issues]
- Expected improvements: [Quantified goals]
- Implementation timeline: [Estimated weeks]

## Priority 1: Critical Fixes (Week 1)
[High-impact, low-effort fixes]
- [ ] Fix 1: Font loading optimization
  - Current issue: Blocking render, causing 5.3s FCP
  - Solution: Add font-display: swap to Google Fonts
  - Expected impact: FCP 5.3s → 2.5s (-53%)
  - Effort: 5 minutes

- [ ] Fix 2: Image optimization
  - Current issue: Large PNG images
  - Solution: Convert to WebP, add width/height
  - Expected impact: LCP 5.8s → 3.5s (-40%)
  - Effort: 30 minutes

[Continue for all Priority 1 fixes]

## Priority 2: Important Improvements (Week 2-3)
[Medium-impact, medium-effort fixes]

## Priority 3: Long-term Enhancements (Month 2+)
[Strategic improvements]

## LLM Optimization Roadmap
[Specific improvements for AI search]

## Monitoring & Verification
- Tools to use
- Metrics to track
- Success criteria

## Resources & Next Steps
- Documentation to reference
- Tools needed
- Support required
```

### Step 8: Implementation Support (If Requested)

If user wants to implement fixes:

1. **For code changes:**
   - Show exact code to modify
   - Explain where files are located
   - Provide before/after examples
   - Test changes locally first

2. **For content changes:**
   - Suggest improved copy
   - Optimize meta tags
   - Enhance structured data
   - Improve internal linking

3. **For configuration changes:**
   - Update Vercel settings
   - Modify build commands
   - Configure caching
   - Set up monitoring

### Step 9: Verification & Testing

After implementing changes:

1. **Use SEO_VERIFICATION.md checklist:**
   - View Page Source
   - Google Rich Results Test
   - Lighthouse SEO Score
   - Social Media Previews
   - PageSpeed Insights

2. **Performance testing:**
   - Lighthouse audit (before/after)
   - PageSpeed Insights (mobile + desktop)
   - Vercel Speed Insights monitoring
   - Real User Monitoring (RUM)

3. **LLM verification:**
   - Test ChatGPT citations
   - Check Perplexity results
   - Verify Claude understanding
   - Google SGE preview

**Output:** Verification Report with results and remaining issues.

## Common SEO Issues & Solutions

### Issue 1: Slow FCP/LCP (Current: 5.3s/5.8s)

**Causes:**
- Font loading blocking render
- Large JavaScript bundle (483.84 KB)
- No code splitting
- Large unoptimized images

**Solutions:**
1. Add `font-display: swap` to Google Fonts URL
2. Implement React.lazy() for code splitting
3. Convert images to WebP format
4. Add width/height to all images
5. Lazy load below-fold images

**Expected Impact:** FCP 5.3s → 2.0s, LCP 5.8s → 2.8s

### Issue 2: Large Bundle Size (483.84 KB)

**Causes:**
- No code splitting
- Unused dependencies
- Entire app loaded upfront
- Framer Motion animations

**Solutions:**
1. Code splitting by route (React.lazy())
2. Tree shaking (remove unused code)
3. Analyze bundle (find large dependencies)
4. Consider lighter animation library or CSS animations

**Expected Impact:** Bundle 483 KB → 250 KB (-48%)

### Issue 3: Missing Structured Data

**Causes:**
- Only basic schemas implemented
- No FAQ schema
- Limited Person schema details
- No Organization schema

**Solutions:**
1. Enhance Person schema (add knowsAbout, sameAs)
2. Add FAQ schema for common questions
3. Add Organization schema if applicable
4. Implement BreadcrumbList for all pages

**Expected Impact:** Better rich snippets, improved AI citations

### Issue 4: Poor Internal Linking

**Causes:**
- Blog posts isolated (no related posts)
- No breadcrumbs
- Limited footer navigation
- No topic clusters

**Solutions:**
1. Add "Related Posts" section to blog posts
2. Implement breadcrumb navigation
3. Create topic clusters (group related articles)
4. Link projects from blog posts

**Expected Impact:** Better crawlability, improved user engagement

### Issue 5: Not Optimized for LLM Search

**Causes:**
- Vague descriptions ("I'm a developer")
- No direct answers
- Missing temporal context (dates, versions)
- Unclear credentials

**Solutions:**
1. Add explicit credentials ("5+ years, 50+ projects")
2. Provide direct answers in first paragraph
3. Add publication/update dates to all content
4. Define technical terms explicitly
5. Use factual, specific language

**Expected Impact:** Better AI citations, improved visibility in ChatGPT/Perplexity

## Best Practices for Portfolio SEO

### Technical Foundation
✅ Prerendering implemented (static HTML)
✅ HTTPS and SSL configured (Vercel)
✅ Mobile-responsive design
✅ Clean URL structure
⏳ Code splitting (to implement)
⏳ Image optimization (to improve)

### Content Strategy
✅ Blog system with markdown posts
✅ Project showcase with descriptions
✅ About section with background
⏳ Regular blog updates (increase frequency)
⏳ Case studies for projects (add detail)
⏳ FAQ section (to add)

### Performance Optimization
✅ CDN (Vercel Edge Network)
✅ Caching configured
✅ CSS minification
⏳ Font loading optimization (critical)
⏳ Code splitting (critical)
⏳ Image optimization (critical)

### LLM Optimization
✅ Semantic HTML structure
✅ Structured data (Person, Article)
⏳ Direct answer format (improve)
⏳ Explicit credentials (enhance)
⏳ FAQ schema (add)

## Tools & Resources

### Analysis Tools
- **Lighthouse** (Chrome DevTools) - Technical audit
- **PageSpeed Insights** - Performance metrics
- **Google Rich Results Test** - Structured data validation
- **Vercel Speed Insights** - Real user monitoring
- **Mobile-Friendly Test** - Mobile optimization

### Monitoring Tools
- **Google Search Console** - Search performance
- **Vercel Analytics** - Traffic analytics
- **Lighthouse CI** - Continuous monitoring

### Testing Tools
- **ChatGPT Search** - LLM citation testing
- **Perplexity** - AI search verification
- **Google SGE** - Search Generative Experience preview

### Reference Documentation
- [seo-checklist.md](references/seo-checklist.md) - Complete SEO checklist
- [llm-optimization.md](references/llm-optimization.md) - LLM optimization guide
- [core-web-vitals.md](references/core-web-vitals.md) - Performance analysis guide

## Output Templates

### Technical SEO Report Template

```markdown
# Technical SEO Audit - [Date]

## Summary
- Overall Score: X/100
- Critical Issues: X
- Warnings: X
- Passed Checks: X

## Meta Tags & Headers
✅ Passed:
- [ ] Unique titles on all pages
- [ ] Meta descriptions present

❌ Issues:
- [ ] Issue 1: Description
  - Impact: High/Medium/Low
  - Fix: Specific solution
  - Effort: Time estimate

## Structured Data
[Same format as above]

## Prerendering
[Same format]

## Recommendations
1. [Priority 1 fixes]
2. [Priority 2 fixes]
3. [Priority 3 fixes]
```

### Performance Report Template

```markdown
# Core Web Vitals Analysis - [Date]

## Current Metrics
| Metric | Current | Target | Status |
|--------|---------|--------|--------|
| FCP    | X.Xs    | < 1.8s | ❌/⚠️/✅ |
| LCP    | X.Xs    | < 2.5s | ❌/⚠️/✅ |
| FID    | Xms     | < 100ms| ❌/⚠️/✅ |
| CLS    | X.XX    | < 0.1  | ❌/⚠️/✅ |

## Bottleneck Analysis
1. [Primary bottleneck]
   - Cause: [Specific issue]
   - Impact: [Metric affected]
   - Fix: [Solution]
   - Expected improvement: [X%]

## Optimization Plan
### Priority 1 (Critical)
- [ ] Fix 1
- [ ] Fix 2

### Priority 2 (Important)
- [ ] Fix 1
- [ ] Fix 2

### Priority 3 (Nice to Have)
- [ ] Fix 1
- [ ] Fix 2
```

### LLM Optimization Report Template

```markdown
# LLM Optimization Analysis - [Date]

## Current LLM Visibility
- ChatGPT Search: [Found/Not Found]
- Perplexity: [Citation Quality: Good/Fair/Poor]
- Claude: [Understanding: Accurate/Partial/Poor]

## Semantic Structure
✅ Strengths:
- [What's working well]

❌ Issues:
- [What needs improvement]

## Content Format
✅ Strengths:
- [Direct answers present]

❌ Issues:
- [Missing direct answers]
- [Vague descriptions]
- [No temporal context]

## Recommendations
1. [Specific improvement]
   - Current: [Example of current text]
   - Improved: [Example of optimized text]
   - Impact: [Expected improvement]

## Implementation Priority
[Ordered list of fixes]
```

## Integration with Other Portfolio Skills

### Related Skills
- **portfolio-frontend-design** - UI/UX consistency when implementing SEO changes
- **portfolio-code-review** - Code quality for SEO improvements
- **portfolio-testing** - Testing SEO implementations
- **portfolio-copywriting** - Content optimization for SEO

### Handoff Points
- After SEO analysis → Use portfolio-copywriting for content improvements
- Before implementing → Use portfolio-code-review for code changes
- After implementation → Use portfolio-testing for verification

## Notes for AI Agents

- **Always read SRS.md and PRD.md first** to understand current state
- **Reference specific files** (PRERENDERING.md, SEO_VERIFICATION.md) for context
- **Use quantifiable metrics** in reports (not vague "improve performance")
- **Prioritize by impact and effort** (Quick wins first)
- **Provide code examples** for implementation
- **Reference Core Web Vitals targets** from core-web-vitals.md
- **Consider LLM optimization** alongside traditional SEO
- **Test recommendations** against portfolio architecture constraints

## Version History

**v1.0** (2025-12-20):
- Initial skill creation
- Technical SEO audit workflow
- Performance analysis with Core Web Vitals
- LLM optimization guide
- Integration with portfolio project documentation
