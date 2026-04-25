# Personal Website Redesign Plan
## Inspired by Huyen Chip's minimalist content-first approach

**Status**: Planning Phase  
**Target**: Production-ready, incremental implementation  
**Timeline**: Phase-based rollout

---

## 📋 AUDIT: Current State Analysis

### Current Stack
- **Static Generator**: Jekyll (Ruby-based)
- **Theme**: Minimal Mistakes (Academic Pages fork)
- **Hosting**: GitHub Pages
- **Build**: `bundle exec jekyll serve`

### Current Structure
- ✅ Seven main layouts (`default.html`, `single.html`, `splash.html`, `talk.html`, `archive.html`, etc.)
- ✅ SCSS architecture with modular files
- ✅ Recent modernization with `_modern.scss` (2024)
- ✅ Core pages: Home, Blog, CV, Summary, Papers, List 100
- ✅ Navigation structure defined in YAML
- ⚠️ Some vestigial academic theme code (author profiles, sidebars)
- ⚠️ Dense styling across multiple SCSS files (needs consolidation)
- ⚠️ Not fully aligned with content-first minimalism yet

### Current Design Issues
1. **Visual Hierarchy**: Competing design signals (sidebars, cards, mixed styles)
2. **Typography**: Good but can be more refined and spacious
3. **Navigation**: Minimal but could be simpler/cleaner
4. **Homepage**: Good prose, but layout could be more elegant
5. **Whitespace**: Adequate, but could be more generous
6. **Blog Post Layout**: Standard, but not optimized for reading flow
7. **Components**: Scattered across multiple SCSS files

### Strengths to Preserve
- ✅ Clean semantic HTML structure
- ✅ Responsive foundation
- ✅ Good typography choices
- ✅ Performance-focused (no JS frameworks)
- ✅ Accessible baseline
- ✅ Existing content organization

---

## 🎨 DESIGN SYSTEM

### Typography
- **Font Stack**: System fonts (faster, cleaner)
  - **Prose**: `-apple-system, BlinkMacSystemFont, "Segoe UI", Helvetica, Arial, sans-serif`
  - **Monospace**: `"Courier New", Courier, monospace` or `"Monaco", monospace`
- **Heading Sizes**:
  - H1: 2.4rem (40px) — Page titles
  - H2: 1.8rem (28px) — Section headers
  - H3: 1.3rem (20px) — Subsections
  - Body: 1rem (16px) — 1.65 line-height
- **Font Weight**: 400 regular, 600 bold (no 700)

### Color Palette
- **Primary**: `#000000` (pure black text)
- **Secondary**: `#666666` (light gray for metadata)
- **Tertiary**: `#999999` (even lighter for hints)
- **Background**: `#ffffff` (pure white, no off-white)
- **Accent**: `#0066cc` (link color, minimal use)
- **Code Background**: `#f5f5f5` (light gray)
- **Code Text**: `#333333` (dark gray)

### Spacing System (8px base)
- `xs`: 4px
- `sm`: 8px
- `md`: 16px
- `lg`: 24px
- `xl`: 32px
- `2xl`: 48px
- `3xl`: 64px

### Layout Grid
- **Max-width**: 800px (reading-optimized)
- **Gutter**: 24px (mobile), 32px (desktop)
- **Container padding**: 24px (mobile), 48px (desktop)

### Component Styles
- **No cards**: All content flows naturally
- **No shadows**: Minimal borders only when needed
- **Border**: `1px solid #e0e0e0` (subtle gray)
- **Hover states**: Color change only (no elevation)
- **Focus states**: Outline style for accessibility

---

## 📐 INFORMATION ARCHITECTURE

### Navigation (Top)
```
[Aniket Velhankar]     Home  Blog  Papers  About  List 100
```
- Left: Wordmark (site name as link to home)
- Right: 5 essential links
- Sticky on scroll
- Mobile: hamburgermenu with same structure

### Pages Structure
1. **Home** (`/`) — Personal essay + latest writing
2. **About** (`/about/`) — Who you are, what you do (expanded)
3. **Blog** (`/blog/`) — All writing, chronological
4. **Papers** (`/papers/`) — Research & reference list
5. **List 100** (`/list-100/`) — 100 goals
6. **Navigation**: Home, Blog, Papers, About, List 100

### Homepage Layout (NEW - Content First)
```
┌─────────────────────────────────────┐
│  Aniket Velhankar (as link)         │
├─────────────────────────────────────┤
│                                     │
│  [Hero prose - 2-3 paragraphs]      │
│  Who you are, what excites you,     │
│  why you build things               │
│                                     │
│  [Social links: GitHub, Email]      │
│                                     │
├─────────────────────────────────────┤
│                                     │
│  ## Latest Writing                  │
│                                     │
│  [Post 1]                           │
│  [Post 2]                           │
│  [Post 3]                           │
│  → View all posts                   │
│                                     │
└─────────────────────────────────────┘
```

### Blog Layout (NEW - Reading Optimized)
```
┌─────────────────────────────────────┐
│  [Title]                            │
│  [Date] · [Read time]               │
│                                     │
│  [Article content]                  │
│  Generous margins, optimal line     │
│  length, clear typography           │
│                                     │
│  ---                                │
│  [Metadata]                         │
│  Tags | Share | Back to blog        │
└─────────────────────────────────────┘
```

### About Page (NEW - Professional Profile)
```
┌─────────────────────────────────────┐
│  About me                           │
│                                     │
│  [Professional summary - prose]     │
│                                     │
│  ## What I do                       │
│  - Deep learning & CV               │
│  - Building production systems      │
│  - Technical writing                │
│                                     │
│  ## Currently                       │
│  [Current role/focus]               │
│                                     │
│  ## Education & Background          │
│  [Timeline-based or prose]          │
│                                     │
│  ## Featured Talks & Projects       │
│  [Link list]                        │
│                                     │
│  [Contact CTA]                      │
└─────────────────────────────────────┘
```

---

## 🛠️ IMPLEMENTATION ROADMAP

### Phase 1: Foundation (This week)
- [ ] Create `_design-system.scss` (variables, typography, spacing)
- [ ] Refactor `_base.scss` (reset, normalize)
- [ ] Clean up `_masthead.html` (top nav)
- [ ] Simplify footer
- [ ] Create `_typography.scss` (heading, body, code styles)

### Phase 2: Core Pages (Next week)
- [ ] Redesign homepage (splash layout)
- [ ] Update about page
- [ ] Create new blog list page
- [ ] Update single blog post layout

### Phase 3: Components & Refinement (Week 3)
- [ ] Implement post cards/links
- [ ] Social share buttons
- [ ] Breadcrumbs (optional)
- [ ] Mobile navigation
- [ ] Form styling (if contact form exists)

### Phase 4: Polish & Deploy (Week 4)
- [ ] Accessibility audit
- [ ] Performance optimization
- [ ] Mobile testing
- [ ] SEO & metadata
- [ ] Deploy to production

### Phase 5: Content Optimization (Ongoing)
- [ ] Update all content for new structure
- [ ] Add missing metadata
- [ ] Optimize images
- [ ] Create recommended reading sections

---

## 📁 FILES TO CHANGE/CREATE

### SCSS Files (Styling)
**Create:**
- `_sass/_design-system.scss` — Color, typography, spacing variables
- `_sass/_typography.scss` — Font sizing, line heights, weights
- `_sass/_layout.scss` — Grid, container, max-width, margins
- `_sass/_components.scss` — Buttons, links, lists, code blocks
- `_sass/_responsive.scss` — Media queries, mobile-first

**Update/Consolidate:**
- `_sass/_base.scss` — Remove redundancy, import system variables
- `_sass/_masthead.html` — Simplify navigation
- `_sass/_footer.html` — Clean footer styling
- Delete: `_sass/_modern.scss` (merge into design system)

### Layout Files (HTML)
**Create:**
- `_layouts/blog.html` — Blog list page
- `_includes/post-meta.html` — Date, reading time, tags

**Update:**
- `_layouts/default.html` — Include new nav/footer
- `_layouts/single.html` — Article optimized layout
- `_layouts/splash.html` — Homepage layout

### Config Files
**Update:**
- `_config.yml` — Update site metadata
- `_data/navigation.yml` — Simplify navigation

### Page Files
**Create (Fresh):**
- `_pages/index.md` — New homepage
- `_pages/blog.md` — Blog list/archive

**Update:**
- `_pages/about.md` — Professional profile
- `_pages/papers.md` — Reference list
- `_pages/list-100.md` — Goal list (keep as-is)

---

## 🎯 KEY DESIGN DECISIONS

1. **No CSS Framework**: Pure CSS for speed and control
2. **System Fonts**: Modern, legible, instant rendering
3. **No JavaScript** (except analytics): Fast, simple, accessible
4. **Grid-based**: 800px max-width for reading comfort
5. **Generous Whitespace**: 24-48px gutters throughout
6. **Black Text**: #000, not warm blacks or grays
7. **Link Colors**: Blue (#0066cc) only, no heavy styling
8. **Monospace Code**: System monospace, simple highlighting
9. **Responsive First**: Mobile-first design approach
10. **Content First**: Structure, then style

---

## 📊 SUCCESS METRICS

- Page load time < 1s (lighthouse)
- Mobile score > 95
- Accessibility > 95
- Reading time visible on posts
- All pages responsive ≤600px width
- Navigation always accessible
- Print-friendly layouts
- Social share links work
- Email signup (optional)

---

## ✨ HUYEN CHIP-INSPIRED ELEMENTS

✅ **Implemented in this plan**:
- Prose-first homepage
- Minimal navigation (5-7 links)
- Generous whitespace
- Clean typography (system fonts)
- Content-focused layout
- Simple color palette (black/white/blue)
- Reading-optimized line length
- Publication-style hierarchy
- Personal essay tone
- Technical credibility

❌ **NOT cloning**:
- Visual design (colors, specific fonts)
- Content topics or examples
- Page structure details
- Micro-interactions
- Specific wording

---

## 🚀 NEXT STEPS

1. ✅ Approve design system colors & typography
2. ✅ Confirm information architecture
3. Start Phase 1: Foundation (SCSS & variables)
4. Build Phase 2: Core page layouts
5. Iterate & refine based on feedback

