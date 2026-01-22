# BitPadLabs Website - GitHub Copilot Instructions

## Project Overview

This is the official website for **BitPadLabs, LLC**, a certified Woman-Owned Small Business (WOSB) providing innovative software development, strategic partnerships, and expert technology consulting for government and commercial clients.

**Site URL:** https://bitpadlabs.com  
**Technology:** Jekyll static site generator  
**Hosting:** GitHub Pages  

## Company Identity

### Certification & Registration
- **WOSB Certified:** January 12, 2026
- **DUNS:** 144845731
- **UEI:** WXU7TJ5MQJW4
- **CAGE:** 15LW1
- **SAM.gov:** Active registration for federal contracting

### Leadership
BitPadLabs is woman-owned and led by three founding members:
- **Hannah Cassels** - CEO (Co-Owner)
- **Jaime Inman** - Chief Operating & Financial Officer (Co-Owner)
- **Melanie Amerson** - Chief Strategy Officer (Co-Owner)
- Christopher Inman - CTO (Founding non-member)
- Ryan Burke - CGO (Founding non-member)

### Strategic Partnerships
- **Miro** - Visual collaboration platform partner
- **Red Hat** - Enterprise open source solutions partner
- Additional partnerships with GitHub, AWS, Azure, and other technology providers

## Site Structure

### Key Pages
- **Home (index.html)** - Hero section, services overview, partnerships preview
- **About (about.html)** - Company story, mission, values, WOSB certification
- **Capabilities (capabilities.html)** - Comprehensive technology services and expertise
- **Partnerships (partnerships.html)** - Strategic partnerships with Miro, Red Hat, and technology ecosystem
- **Team (team.html)** - Leadership team profiles
- **Blog (blog.html)** - Company news, announcements, and updates
- **Tech Stack (tech-stack.html)** - Technologies and tools used in service delivery
- **Contact (contact.html)** - Contact information and inquiry form
- **FAQ (faq.html)** - Frequently asked questions about services
- **Terms (terms.html)** - Terms of service
- **Privacy (privacy.html)** - Privacy policy

### Data Files (_data/)
- **naics.yml** - NAICS codes for federal contracting
- **team.yml** - Team member profiles (order: Hannah, Jaime, Melanie, Christopher, Ryan)

### Includes (_includes/)
- **header.html** - Site navigation (Home, About, Team, Capabilities, Partnerships, Blog, Contact)
- **footer.html** - Footer with WOSB logo, navigation, contracting details, NAICS codes
- **cookie-consent.html** - Cookie consent banner

### Layouts (_layouts/)
- **default.html** - Base template
- **post.html** - Blog post template

### Posts (_posts/)
Blog posts use YAML front matter with format: `YYYY-MM-DD-title.md`

Current posts:
- `2026-01-12-wosb-certification.md` - WOSB certification announcement
- `2025-07-13-bitpad-labs-launch.md` - Company launch announcement

## Design System

### Brand Colors
```yaml
frog_green: "#4CAF50"     # Primary brand color
leafy_green: "#388E3C"    # Darker green accent
red_eye: "#EF3B2C"        # Alert/accent red
sunny_yellow: "#FFEB3B"   # Highlight yellow
chip_black: "#1C1C1C"     # Primary text
soft_beige: "#FDF7F0"     # Background
```

### Typography
- **Headings:** Poppins, Montserrat (fallback)
- **Body:** Helvetica Neue, Arial (fallback)
- **Base font size:** 16px
- **Line height:** 1.6

### Components

#### Cards
All card components include hover effects:
- **Border-left:** 4px solid transparent (default) → $frog-green (hover)
- **Transform:** translateY(-5px) on hover
- **Box-shadow:** Enhanced on hover

```scss
.card {
  background-color: white;
  border-radius: $border-radius-md;
  box-shadow: $shadow-md;
  transition: transform $transition-base, box-shadow $transition-base, border-left $transition-base;
  border-left: 4px solid transparent;
  
  &:hover {
    transform: translateY(-5px);
    box-shadow: $shadow-lg;
    border-left-color: $frog-green;
  }
}
```

#### Buttons
- **Primary:** Green background (#4CAF50)
- **Secondary:** Outline style
- **Third:** Alternative style for tertiary actions

### Spacing
```scss
$spacing-xs: 7.5px
$spacing-sm: 15px
$spacing-md: 30px
$spacing-lg: 45px
$spacing-xl: 60px
```

### Breakpoints
```scss
$breakpoint-xs: 375px
$breakpoint-sm: 576px
$breakpoint-md: 768px
$breakpoint-lg: 992px
$breakpoint-xl: 1200px
```

## Content Guidelines

### Messaging Priorities
1. **WOSB Certification** - Highlight woman-owned status and federal contracting capabilities
2. **Service Focus** - Emphasize consulting, partnerships, and custom development over products
3. **Strategic Partnerships** - Feature Miro, Red Hat, and technology ecosystem
4. **Quality & Expertise** - Showcase team experience, certifications, and proven capabilities
5. **Privacy & Security** - Privacy-first design, security as foundational principle

### Tone & Voice
- **Professional but approachable** - Not corporate, not casual
- **Confident and capable** - Showcase expertise without being arrogant
- **Clear and direct** - Avoid jargon when possible, explain technical concepts
- **Human-centered** - Focus on solving real problems for real people

### Avoided Terms (De-productized)
- ❌ "Products" (replaced with "Services" or "Solutions")
- ❌ "Portfolio" (replaced with "Capabilities")
- ❌ Product names: GlowStatus, BudsyApp (removed from site)
- ❌ "Software lab" (replaced with service-oriented language)

## Development Guidelines

### File Organization
```
bitpadlabs-site/
├── _config.yml           # Site configuration
├── _data/                # Data files (YAML)
├── _includes/            # Reusable components
├── _layouts/             # Page templates
├── _posts/               # Blog posts
├── _sass/                # SCSS stylesheets
│   ├── _base.scss        # Base styles and components
│   ├── _layout.scss      # Layout-specific styles
│   ├── _variables.scss   # Design tokens
│   └── _portfolio-cards.scss # Card component styles
├── _site/                # Generated site (ignored)
├── assets/
│   ├── css/              # Compiled CSS
│   ├── images/           # Images and logos
│   │   ├── decals-and-icons/  # SBA certification badges
│   │   ├── SBA-Logo-PNG/      # SBA logo files
│   │   ├── partnerships/      # Partner logos
│   │   └── team/              # Team member photos
│   └── js/               # JavaScript files
├── *.html                # Top-level pages
└── .github/              # GitHub configuration
```

### Adding New Blog Posts

1. Create file: `_posts/YYYY-MM-DD-title.md`
2. Add front matter:
```yaml
---
layout: post
title: "Post Title"
date: YYYY-MM-DD HH:MM:SS
author: BitPadLabs Team
categories: [category1, category2]
tags: [tag1, tag2]
image: /assets/images/featured-image.png
excerpt: "Brief summary for previews and SEO"
---
```
3. Write content in Markdown
4. Images should be optimized and stored in `/assets/images/`

### Adding Team Members

Edit `_data/team.yml`:
```yaml
- name: Full Name
  role: Job Title
  github: username  # optional
  image: filename.jpg  # store in assets/images/team/
  bio: >-
    Multi-line biography describing role and expertise.
```

**Order requirement:** Hannah, Jaime, Melanie should be listed first (owners), followed by Christopher and Ryan last.

### Updating Navigation

Edit `_includes/header.html` to modify main navigation menu. Current order:
1. Home
2. About Us
3. Our Team
4. Capabilities
5. Partnerships
6. Blog
7. Contact

### Adding Partnership Information

Edit `partnerships.html` to add new strategic partnerships. Include:
- Partner logo (if approved) in `/assets/images/partnerships/`
- Partnership overview
- Services delivered
- Use cases
- Technology areas

#### Miro Partnership Logos

Miro brand assets are available in `/assets/images/partnerships/`:
- `MiroLogo-blackyellow.svg` - **Primary logo** - Black text with yellow dot (use for light backgrounds)
- `MiroLogo-whiteyellow.svg` - White text with yellow dot (for dark backgrounds)
- `MiroLogo-black.svg` - Black monochrome logo (light backgrounds)
- `MiroLogo-white.svg` - White monochrome logo (dark backgrounds)
- `MiroLogo-blacknegative.svg` - Black logo negative version (special uses)

**Logo Usage Guidelines (from Miro Brand Kit):**

**Priority:**
- Full logo lockup (icon + wordmark) should be prioritized whenever possible
- The icon symbol can be used standalone only in tight spaces (app icons, social media avatars, slides)
- Legibility should always be at the forefront

**Clear Space:**
- Always give the Miro logo breathing room
- Maintain minimum buffer zone around logo to avoid overlapping elements

**Minimum Size:**
- **Digital:** Never smaller than 60px
- **Print:** Never smaller than 2cm (300dpi vs 72dpi resolution difference)

**Color Selection:**
- Choose logo color based on background elements to ensure maximum contrast and clarity
- Use full color versions (blackyellow/whiteyellow) for primary applications
- Use one-color versions (black/white) when color is limited

**Co-Branding:**
- If placing alongside other logos, separate with element "X"
- Distance between logos and separator: 2X on both sides
- Minimum buffer zone: 2X surrounding each logo

**Don'ts:**
- Don't modify, rotate, or distort logos
- Don't change logo colors
- Don't reproduce smaller than minimum sizes
- Don't compromise legibility

**Miro Brand Colors:**
- **Primary:** Miro Hero Yellow (#FFDD33) - Master brand color, should be dominant
- **Breakthrough Black:** #1C1C1E
- **Workspace White:** #FFFFFF
- **Secondary Palette:** Dark Green (#6EDB8C), Purple-Pink (#CE70FC), Blue (#57D2F7), Cyan (#47D1C4), Red (#FF6683), Orange (#FF9C57)

**Typography:**
- **Brand Typeface:** Roobert Pro (custom font with Stylistic Sets 1 & 4)
- **Headline Style:** Heavy Italic, Uppercase for short headlines (max 5 words)
- **Highlighting:** Yellow highlight for key words/phrases (0.75X padding, 1.5X line spacing)

**Photography Art Direction:**
- Yellow tones predominant
- Active, authentic, inclusive, collaborative imagery
- Natural lighting (golden hour preferred)
- Real work environments beyond just offices
- Product-first approach when showing Miro interface

**Reference:**
- Official brand guidelines: https://brandkit.miro.com/
- Logo guidelines: https://brandkit.miro.com/corporate-visual-identity/the-miro-logo-2
- Colors: https://brandkit.miro.com/corporate-visual-identity/colors
- Typography: https://brandkit.miro.com/corporate-visual-identity/typography-2
- Photography: https://brandkit.miro.com/corporate-visual-identity/photography
- Logo usage governed by Miro Solutions Partner Program Agreement (Section 3.1-3.2)

## SEO & Meta Tags

### Site-wide
Configured in `_config.yml`:
```yaml
title: BitPadLabs
description: >-
  Small bytes. Big leaps. BitPadLabs is a certified Woman-Owned Small Business (WOSB) 
  delivering innovative software development, strategic partnerships, and expert technology 
  consulting for government and commercial clients.
```

### Page-specific
Use front matter:
```yaml
title: Page Title
description: Page-specific meta description
image: /assets/images/og-image.png  # For social sharing
```

### Blog Posts for LinkedIn
Include:
- **image:** High-quality featured image (1200x630px recommended)
- **excerpt:** Compelling summary for social previews
- Clear, professional content optimized for sharing

## Build & Deployment

### Local Development
```bash
bundle install
bundle exec jekyll serve
# Visit http://localhost:4000
```

### Build
```bash
bundle exec jekyll build
# Output in _site/
```

### Deployment
Site is automatically deployed via GitHub Pages when pushing to main branch.

## Common Tasks

### Adding a New Service/Capability
1. Update `capabilities.html` with new service description
2. Consider adding to homepage `index.html` features section
3. Update `tech-stack.html` if new technologies are involved
4. Optionally create a blog post announcing the new capability

### Partnership Updates
1. Add partner logo to `/assets/images/partnerships/`
2. Update `partnerships.html` with partnership details
3. Add to homepage partnerships preview if top-tier partner
4. Update `capabilities.html` to reference partnership if relevant
5. Consider blog post announcement

### WOSB/Certification Updates
1. Update certification badge images in `/assets/images/decals-and-icons/`
2. Update footer logo reference in `_includes/footer.html`
3. Update about page certification section in `about.html`
4. Update config description if certification status changes

## Sister Company

**BitPadLabs Government Solutions LLC (BPL-GS)** is a related Service-Disabled Veteran-Owned Small Business (SDVOSB) focused on VA and federal contracting. Site located in `bitpadlabsgs-site/` subdirectory. The two companies collaborate but maintain separate branding and certifications.

## Support

**Contact:** info@bitpadlabs.com  
**GitHub:** @BitPadLabs  
**Location:** Georgia and Mississippi

---

*Last updated: January 22, 2026*
