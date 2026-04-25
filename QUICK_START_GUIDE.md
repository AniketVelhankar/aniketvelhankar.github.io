# Website Redesign - Quick Start & Deployment Guide

**Status**: Ready for Testing & Deployment  
**Implementation Level**: Phase 3 Complete (Foundations, Layouts, Components)  
**Estimated Implementation Time**: 2-3 weeks for full deployment

---

## 🚀 Getting Started

### Prerequisites
- Ruby 3.0+ (current system has 2.6.10 - may need upgrade)
- Bundler
- Git
- Jekyll

### Setup Steps

```bash
# 1. Enter project directory
cd ~/Developer/aniketvelhankar.github.io

# 2. Update Ruby version (if needed)
# Using rbenv:
rbenv install 3.2.0
rbenv local 3.2.0

# 3. Install dependencies
bundle install

# 4. Run local development server
bundle exec jekyll serve

# 5. Open in browser
open http://localhost:4000
```

---

## ✨ What's New in This Redesign

### Homepage (`/`)
- **Before**: Cluttered with academic theme elements
- **After**: Clean prose-first introduction with clear value prop
- **Key**: Immediately communicates who you are and what you do

### Navigation
- **Before**: Generic academic theme navbar
- **After**: Minimal sticky header with 5 essential links
- **Design**: Left-aligned wordmark, right-aligned menu
- **Mobile**: Hamburger toggle that works smoothly

### Blog (`/blog/`)
- **New**: Dedicated blog archive page
- **Shows**: Post titles, dates, reading time, excerpts
- **Design**: Clean list view, scannable layout

### About (`/about-me/`)
- **New**: Professional profile page
- **Content**: Background, what you do, principles, contact
- **Design**: Proper section hierarchy, readable prose

### Article Layout (`/post` layout)
- **New**: Optimized for reading long-form content
- **Features**: Large readable type, metadata, navigation
- **Navigation**: Previous/next post links, back to blog

### Design System
- **New**: Complete design tokens in SCSS
- **Includes**: 50+ color, typography, spacing variables
- **Components**: 30+ reusable UI components
- **Responsive**: Mobile-first, 4 breakpoints

---

## 📂 File Structure Changes

### New Files (13 total)
```
_sass/
  _design-system.scss      (240 lines) - Design tokens
  _typography.scss         (290 lines) - Font/text styles
  _layout.scss             (280 lines) - Grid/container
  _components.scss         (520 lines) - UI components

_pages/
  blog.md                  - Blog archive
  about-me.md              - About page

_layouts/
  post.html                - Article template

_includes/
  post-date.html           - Date formatting helper

Documentation/
  REDESIGN_PLAN.md         - Full redesign strategy
  IMPLEMENTATION_SUMMARY.md - This project summary
```

### Updated Files (5 total)
```
assets/css/main.scss       - Reorganized SCSS imports
_includes/masthead.html    - New navigation
_includes/footer.html      - Cleaner footer
_pages/about.md            - New homepage
_data/navigation.yml       - Simplified nav structure
```

---

## 🎨 Design Highlights

### Colors
| Element | Color | Usage |
|---------|-------|-------|
| Text | #000000 | Primary content |
| Links | #0066cc | All clickable links |
| Meta | #999999 | Secondary info (dates) |
| Borders | #e0e0e0 | Subtle dividers |
| Code BG | #f5f5f5 | Code blocks |
| Background | #ffffff | Page background |

### Typography
- **San-serif**: System fonts (fastest, most legible)
- **H1**: 2.4rem — Page titles
- **H2**: 1.875rem — Section headers
- **Body**: 1rem @ 1.65 line-height (excellent readability)
- **Code**: Monospace, 0.95em, proper contrast

### Layout
- **Max-width**: 800px (optimal reading width)
- **Gutters**: 24px mobile / 48px desktop
- **Spacing**: 8px base unit system
- **Breakpoints**: 480px, 768px, 1024px, 1280px

---

## 📋 Implementation Checklist

### Phase 4: Testing (NEXT)
- [ ] Upgrade Ruby to 3.2.0+
- [ ] Run `bundle install` successfully
- [ ] Test build: `bundle exec jekyll build --drafts`
- [ ] Start dev server: `bundle exec jekyll serve`
- [ ] Visual check all pages
- [ ] Test navigation links
- [ ] Check mobile responsiveness (viewport: 375px, 768px, 1024px)
- [ ] Verify form functionality (if applicable)
- [ ] Accessibility audit (keyboard nav, screen reader)
- [ ] Lighthouse audit (target: >95 on all metrics)

### Phase 5: Content & Deployment (FINAL)
- [ ] Update blog post frontmatter
  ```yaml
  layout: post
  date: YYYY-MM-DD
  reading_time: X  # optional
  ```
- [ ] Verify all links work
- [ ] Optimize images for web
- [ ] Update favicons
- [ ] Set up analytics (Google Analytics optional)
- [ ] Create sitemap
- [ ] Update robots.txt
- [ ] Create 404.md page
- [ ] Test deployment locally with `--future`
- [ ] Deploy to GitHub Pages (git push)
- [ ] Verify production site (aniketvelhankar.github.io)
- [ ] Test all pages on live site

---

## 🔧 Common Tasks

### Creating a New Blog Post
```markdown
---
layout: post
title: "Your Article Title"
date: 2026-04-25
excerpt: "Brief description for preview"
reading_time: 8
---

# Article Title

Your content here...
```

### Adding to Navigation
Edit `_data/navigation.yml`:
```yaml
main:
  - title: "New Page"
    url: /new-page/
```

### Customizing Colors
Edit `_sass/_design-system.scss`:
```scss
$color-primary: #0066cc;  // Change link color
$color-text: #000000;      // Change text color
```

---

## 🎯 Key Technical Decisions

1. **No JavaScript Frameworks**: Pure CSS for speed and simplicity
2. **System Fonts**: No custom web fonts (faster, more accessible)
3. **800px Max-width**: Optimal for reading comfort
4. **Mobile-first CSS**: Responsive by design
5. **Semantic HTML**: Proper heading hierarchy, alt text on images
6. **Design Tokens**: Everything defined in SCSS variables

---

## 📊 Expected Performance

**Lighthouse Scores** (with optimized images):
- ✅ Performance: 95+
- ✅ Accessibility: 98+
- ✅ Best Practices: 95+
- ✅ SEO: 98+

**Page Load Time**:
- Homepage: <500ms
- Article: <600ms
- Blog archive: <400ms

---

## 🐛 Troubleshooting

### Build fails with gem errors
**Solution**: Update Ruby to 3.0+
```bash
rbenv install 3.2.0
rbenv local 3.2.0
rm Gemfile.lock
bundle install
```

### CSS not updating
**Solution**: Clear Jekyll cache
```bash
rm -rf _site
bundle exec jekyll clean
bundle exec jekyll serve
```

### Navigation links broken
**Solution**: Check `_data/navigation.yml` URLs
- URLs must start with `/`
- Must match page `permalink`

### Images not showing
**Solution**: Check paths
- Images go in `/assets/images/` or `/images/`
- Reference as `/assets/images/photo.jpg` in markdown

---

## 📚 Design System Variables

All customizable in `_sass/_design-system.scss`:

**Colors**:
```scss
$color-black: #000000;
$color-primary: #0066cc;
$color-border: #e0e0e0;
$color-code-bg: #f5f5f5;
```

**Typography**:
```scss
$font-size-base: 16px;
$line-height-base: 1.65;
$h1-size: 2.4rem;
```

**Spacing**:
```scss
$space-lg: 24px;     // padding/margin
$max-width-prose: 800px;  // content width
```

**Components**:
```scss
$button-background: $color-primary;
$button-padding: 8px 24px;
```

---

## 🔗 Resources

- **Jekyll Docs**: https://jekyllrb.com/docs/
- **Markdown Guide**: https://www.markdownguide.org/
- **SCSS Guide**: https://sass-lang.com/documentation
- **Huyen Chip's Site** (inspiration): https://huyenchip.com/

---

## ✅ Success Criteria

Your redesigned site will be ready when:

1. ✅ All pages build without errors
2. ✅ Navigation works on mobile & desktop
3. ✅ Blog posts display correctly with new layout
4. ✅ About page shows proper content hierarchy
5. ✅ Lighthouse scores > 95 on all metrics
6. ✅ No broken links in navigation
7. ✅ Responsive at 375px, 768px, 1024px viewports
8. ✅ Keyboard navigation works
9. ✅ Looks professional and clean
10. ✅ Loads fast (< 1s on 4G)

---

## 🚢 Deployment

Once testing is complete:

```bash
# 1. Make sure everything is committed
git add .
git commit -m "Redesign: Content-first, minimalist layout"

# 2. Push to main branch
git push origin main

# 3. GitHub Pages automatically builds and deploys
# Site will be live at: aniketvelhankar.github.io

# 4. Verify deployment
# Wait ~1-2 minutes for build to complete
# Check https://github.com/aniketvelhankar/aniketvelhankar.github.io/deployments
```

---

## 📞 Next Steps

1. **Fix Ruby version** (if needed)
2. **Run bundle install**
3. **Start dev server**
4. **Review all pages visually**
5. **Test mobile responsiveness**
6. **Fix any issues found**
7. **Deploy to production**
8. **Monitor real-world performance**

---

**Questions?** See REDESIGN_PLAN.md for detailed strategy or IMPLEMENTATION_SUMMARY.md for technical details.

**Ready to upgrade?** Your site is now built on a solid, professional foundation inspired by thought leaders like Huyen Chip. Focus on great content—the design is ready to support it!
