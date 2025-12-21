# Portfolio SEO Skill - Przegląd

## Opis

Kompleksowy skill do analizy SEO i optymalizacji projektu portfolio. Obejmuje:

- **Audyt techniczny SEO** - meta tagi, structured data, prerendering, sitemap
- **Analiza wydajności** - Core Web Vitals (FCP, LCP, CLS, TBT, TTI)
- **Optymalizacja treści** - headings, keywords, internal linking
- **Optymalizacja dla LLM** - ChatGPT Search, Perplexity, Claude, Google SGE
- **Plan działania** - priorytetyzacja i implementacja ulepszeń

## Zawartość skila

### Główny plik
- **SKILL.md** - Workflow analizy SEO, best practices, templates raportów

### Pliki referencyjne
- **references/seo-checklist.md** - Kompleksowa checklist SEO (200+ punktów)
- **references/llm-optimization.md** - Przewodnik po optymalizacji dla AI search
- **references/core-web-vitals.md** - Analiza wydajności i Core Web Vitals

## Kiedy używać

Użyj tego skila gdy:
- Chcesz przeanalizować obecny stan SEO strony portfolio
- Potrzebujesz audytu technicznego (meta tagi, structured data)
- Analizujesz wydajność (Core Web Vitals, bundle size)
- Przygotowujesz plan optymalizacji SEO
- Optymalizujesz treść dla wyszukiwarek AI (ChatGPT, Perplexity)
- Weryfikujesz zmiany SEO po wdrożeniu

## Workflow

1. **Initial Assessment** - Zbieranie informacji o obecnym stanie
2. **Technical SEO Audit** - Audyt meta tagów, structured data, prerendering
3. **Performance Analysis** - Analiza Core Web Vitals i bottlenecków
4. **Content Optimization** - Optymalizacja treści dla tradycyjnego SEO
5. **LLM Optimization** - Optymalizacja dla wyszukiwarek AI
6. **Competitive Analysis** - Porównanie z konkurencją (opcjonalne)
7. **Generate SEO Plan** - Kompleksowy plan działania
8. **Implementation Support** - Wsparcie przy implementacji (opcjonalne)
9. **Verification & Testing** - Weryfikacja wdrożonych zmian

## Kluczowe funkcje

### Audyt techniczny
✅ Meta tagi (title, description, OG, Twitter Cards)
✅ Structured data (JSON-LD schemas)
✅ Prerendering verification
✅ URL structure
✅ Sitemap i robots.txt
✅ Internal/external linking

### Analiza wydajności
✅ Core Web Vitals (FCP, LCP, FID, CLS, TTI)
✅ Bundle size analysis
✅ Image optimization
✅ Font loading optimization
✅ Code splitting recommendations

### Optymalizacja LLM
✅ Semantic HTML structure
✅ Direct answer format
✅ Structured data dla LLMs
✅ Citation-friendly content
✅ Testing z ChatGPT/Perplexity/Claude

### Raporty
✅ Technical SEO Report
✅ Performance Report (Core Web Vitals)
✅ LLM Optimization Report
✅ Comprehensive SEO Plan
✅ Verification Report

## Integracja z dokumentacją projektu

Skill jest ściśle zintegrowany z dokumentacją portfolio:

- **docs/portfolio/SRS.md** - Specyfikacja techniczna (baseline metrics)
- **docs/portfolio/PRD.md** - Wymagania produktowe
- **docs/portfolio/seo/PRERENDERING.md** - Dokumentacja prerenderingu
- **docs/portfolio/seo/SEO_VERIFICATION.md** - Checklist weryfikacji

## Znane problemy projektu (z SRS.md)

Skill jest świadomy obecnych problemów wydajnościowych:

| Metric | Current | Target | Status |
|--------|---------|--------|--------|
| FCP | 5.3s | < 1.8s | ❌ Critical |
| LCP | 5.8s | < 2.5s | ❌ Critical |
| TBT | 78ms | < 200ms | ✅ Good |
| CLS | 0 | < 0.1 | ✅ Good |
| TTI | 5.8s | < 3.5s | ⚠️ Needs work |

**Bundle Size:**
- Current: 483.84 KB (gzip: 155.43 KB)
- Target: < 300 KB

## Przykładowe użycie

### Pełny audyt SEO
```
Przeprowadź pełny audyt SEO mojej strony portfolio
```

### Analiza wydajności
```
Przeanalizuj Core Web Vitals i przygotuj plan optymalizacji wydajności
```

### Optymalizacja dla AI search
```
Zoptymalizuj treść strony pod wyszukiwania w ChatGPT i Perplexity
```

### Weryfikacja po wdrożeniu
```
Zweryfikuj czy zmiany SEO zostały poprawnie wdrożone
```

## Narzędzia używane przez skill

### Analiza
- Lighthouse (Chrome DevTools)
- PageSpeed Insights
- Google Rich Results Test
- Vercel Speed Insights

### Monitoring
- Google Search Console
- Vercel Analytics
- Lighthouse CI

### Testing LLM
- ChatGPT Search
- Perplexity
- Google SGE

## Output formats

Skill generuje następujące raporty:

1. **Technical SEO Report** - Audyt techniczny z priorytetyzacją
2. **Performance Report** - Analiza Core Web Vitals z konkretami
3. **LLM Optimization Report** - Rekomendacje dla AI search
4. **Comprehensive SEO Plan** - Plan działania z timelineem
5. **Verification Report** - Wyniki po wdrożeniu

## Powiązane skille

- **portfolio-frontend-design** - Spójność UI/UX przy zmianach SEO
- **portfolio-code-review** - Code review dla zmian SEO
- **portfolio-testing** - Testowanie implementacji SEO
- **portfolio-copywriting** - Optymalizacja treści SEO

## Technologie

Skill jest dostosowany do stack technologicznego projektu:

- React 19.2.0 + Vite 7.2.2
- Tailwind CSS 3.4.18
- Framer Motion 12.23.24
- Puppeteer (prerendering)
- Vercel (deployment)

## Licencja

Apache-2.0 - Zobacz LICENSE.txt dla szczegółów

## Wersja

**v1.0** (2025-12-20)
- Initial release
- Technical SEO audit
- Performance analysis
- LLM optimization
- Integration z dokumentacją portfolio
