# CLAUDE.md - Cowosedlice.cz Project Documentation

## Project Overview

**Cowosedlice.cz** is a Jekyll-based static website for a coworking space located in Novosedlice near Teplice, Czech Republic. The site serves as the primary online presence for this shared office space, showcasing facilities, pricing, member profiles, and contact information.

**Domain:** cowosedlice.cz (www.cowosedlice.cz 301s to it)
**Repository:** github.com/cowosedlice/cowosedlice.cz
**Technology:** Jekyll static site generator hosted on Cloudflare (assets-only Worker `cowosedlice-cz`)
**Language:** Czech (česky)

## Project Purpose

Cowosedlice is a coworking space targeting freelancers (OSVČ) who:
- Need more than just working from home
- Require reliable internet and professional workspace
- Want a community of like-minded professionals
- Work primarily with laptops (IT professionals, developers, etc.)

The website has been running for 3+ years (as of June 2019) without subsidies, funded entirely by member contributions.

## Technologies Used

### Core Framework
- **Jekyll** - Static site generator
- **Cloudflare Workers** - Hosting platform (static assets, `wrangler.jsonc`)
- **Kramdown** - Markdown processor

### Frontend Stack
- **Bootstrap** (3.x) - Responsive CSS framework
- **jQuery** (1.11.0) - JavaScript library
- **Font Awesome** - Icon font library
- **Google Maps API** - Interactive location map

### JavaScript Libraries
- `jquery-1.11.0.js` - Core jQuery library
- `jquery.easing.min.js` - Smooth scrolling animations
- `bootstrap.js` - Bootstrap framework
- `cbpAnimatedHeader.js` - Animated navigation header
- `classie.js` - Class manipulation utilities
- `agency.js` - Main site functionality
- `map.js` - Google Maps integration
- `pano2vr_player.js` - 3D panorama viewer

## Project Structure

```
cowosedlice.cz/
├── _config.yml              # Jekyll configuration and site content
├── _layouts/
│   ├── default.html         # Main layout template
│   └── style.css            # Additional layout styles
├── _includes/               # Reusable HTML components
│   ├── header.html          # Navigation and hero section
│   ├── team.html            # Active members section
│   ├── portfolio_grid.html  # Photo gallery
│   ├── about.html           # Equipment/facilities section
│   ├── services.html        # Services section
│   ├── map.html             # Location map
│   ├── price.html           # Pricing table
│   ├── contact.html         # Contact information
│   ├── footer.html          # Footer with social links
│   ├── modals.html          # Modal dialogs
│   ├── js.html              # JavaScript includes
│   ├── head.html            # HTML head section
│   └── css/                 # CSS partials
│       ├── agency.css       # Custom styles
│       ├── bootstrap.min.css
│       └── map.css
├── _data/                   # Data files
│   └── template.yml         # Template data
├── _plugins/                # Jekyll plugins
│   └── hex_to_rgb.rb        # Color conversion plugin
├── _posts/                  # Blog posts (used for portfolio/gallery)
│   └── 2014-07-*.markdown   # Portfolio item posts
├── .github/
│   └── workflows/
│       ├── deploy.yml         # Build, deploy to Cloudflare, PR previews and checks
│       ├── link-checker.yml   # lychee over the built site
│       ├── claude.yml, claude-code-review.yml
├── img/                     # Images
│   ├── about/               # Facility images
│   ├── team/                # Member photos
│   ├── photos/              # Gallery images
│   ├── portfolio/           # Portfolio items
│   └── logos/               # Logo assets
├── css/                     # Stylesheets
│   └── font-awesome/        # Font Awesome library
├── js/                      # JavaScript files
├── pohled3d/                # 3D panorama viewer
│   ├── index.html
│   ├── cowosedlice.html
│   └── pano2vr_player.js
├── .ruby-version            # Ruby version specification (3.3.6)
├── index.html               # Home page
├── style.css                # Main stylesheet
├── feed.xml                 # RSS feed
├── favicon.ico              # Site favicon
├── 404.html                 # Not-found page (the home page with a 404 status)
├── wrangler.jsonc           # Cloudflare Worker config (custom domain, _site/)
├── www-redirect/            # Tiny Worker: www.cowosedlice.cz -> cowosedlice.cz (301)
├── package.json, package-lock.json  # wrangler, Playwright, Lighthouse (pinned exactly)
├── playwright.config.js, tests/     # Visual regression: PR preview vs production
├── Gemfile                  # Ruby dependencies
├── Gemfile.lock             # Locked dependency versions
├── CLAUDE.md                # AI assistant project documentation
└── README.md                # Development instructions
```

## Site Sections

### 1. Navigation
Located in `_includes/header.html`
- Lidé (People/Team)
- Fotogalerie (Photo Gallery)
- Vybavení (Equipment)
- Mapa (Map)
- Ceník (Pricing)
- Kontakt (Contact)

### 2. Header/Hero Section
- Coworking introduction
- Background image (`img/header-bg.jpg`)
- Description of coworking concept

### 3. Team Section (`_includes/team.html`)
Active members with profiles:
- Radim Klaška (Drupal developer for Morpht Pty. Ltd. and Drupal.cz)
- Jan Nedvěd (Steel construction designer)
- Multiple "Volné místo" (Available slots) showing open positions

### 4. Photo Gallery (`_includes/portfolio_grid.html`)
Visual showcase of the coworking space with thumbnails and full-size images.

### 5. Equipment Section (`_includes/about.html`)
Facilities and amenities:
- High-speed internet (50/25 and 30/10 Mbps from two independent providers)
- Dedicated workspace for permanent members (24/7 access)
- Unlimited coffee from Frolík
- Kitchen area (fridge, microwave, kettle)
- Nearby dining options (restaurants, pizza, food delivery)
- Transportation options (parking, public buses, bike storage)

### 6. Map Section (`_includes/map.html`)
Interactive Google Maps integration showing location:
- Address: Míru 218, Novosedlice, 417 31

### 7. Pricing Section (`_includes/price.html`)
Three pricing tiers:
- **Daily rate**: 300 Kč per day (2 free trial days for new members)
- **Medium plan**: 2000 Kč/month (10 working days, 8:00-17:00, flexible seating)
- **Large plan**: 3500 Kč/month (24/7 access, dedicated workspace)

All plans include: WiFi, printer, PC, kitchen, fridge, coffee maker, etc.

### 8. Contact Section (`_includes/contact.html`)
Contact information:
- Phone: Radim Klaška at +420 605 271 780
- Physical address: Míru 218, Novosedlice, 417 31
- Email: radim@cowosedlice.cz (configured in `_config.yml`)
- Social media links (Facebook, GitHub) in footer

### 9. Footer (`_includes/footer.html`)
Social media links and copyright information.

## Configuration

The `_config.yml` file contains all site configuration and content:

```yaml
url: http://www.cowosedlice.cz
title: Cowosedlice.cz - sdílená kancelář v Novosedlicích u Teplic
email: radim@cowosedlice.cz
description: "Cowosedlice jsou tu pro ty, kterým nevyhovuje práce z domova..."

# Content sections are configured with YAML data structures
history: # Equipment list
price: # Pricing tiers
people: # Team members
social: # Social media links
address: # Physical address

# Build settings
markdown: kramdown
permalink: pretty
exclude:
  - CLAUDE.md  # Exclude this documentation from builds
  - Gemfile
  - Gemfile.lock
  - README.md
  - vendor/
```

## Development Setup

### Prerequisites
- Ruby development environment
- Jekyll and Bundler gems

### Installation (Ubuntu 16.04)
```bash
sudo apt install ruby-dev gcc make libghc-zlib-dev
gem install rubygems-update
gem install jekyll bundler
```

For other systems, see https://jekyllrb.com/

### Install Dependencies
```bash
bundle install
```

### Local Development Server
```bash
bundle exec jekyll serve
```

The site will be available at `http://localhost:4000`

### Build for Production
```bash
bundle exec jekyll build
```

Generated files will be in the `_site/` directory.

## Deployment

Hosted on Cloudflare as an assets-only Worker `cowosedlice-cz` serving the Jekyll build
(`_site/`). Same setup as https://cfsite.klaska.net (repo radimklaska/cfsite): copy
improvements from there. `.github/workflows/deploy.yml`:

- **Push to `main`**: `bundle exec jekyll build`, then `npx wrangler deploy` ->
  https://cowosedlice.cz. A manual "Run workflow" deploys only from `main`.
- **Pull request**: a Workers Preview `pr-<N>` on workers.dev (noindex), and a new PR
  comment per deploy (preview, commit, run, QR code, Visual and Lighthouse rows; older
  ones collapsed). Visual regression compares every page of the preview with production;
  a PR that changes how a page looks (prices, members) fails it on purpose, and the
  comment links a page with the differences. Lighthouse scores the home page.
- **PR closed**: the preview is deleted.
- Secrets: `CLOUDFLARE_API_TOKEN` (deploy token "cowosedlice.cz GitHub Actions deploy":
  Workers Scripts Edit + Account Settings Read, Workers Routes Edit + Zone Read on
  cowosedlice.cz), `CLOUDFLARE_ACCOUNT_ID`, `CLAUDE_CODE_OAUTH_TOKEN`.
- **www**: `www.cowosedlice.cz` is a second, tiny Worker `cowosedlice-cz-www`
  (`www-redirect/`, deployed by the same workflow after the site) that 301s to
  `https://cowosedlice.cz/<path>?<query>`, so the site's Worker stays assets-only.
  Same as https://cfsite.klaska.net/hosting/#www.
- Analytics: Cloudflare Web Analytics, injected by the zone (no tag in the templates).
- Local check: `bundle exec jekyll build && npx wrangler dev`.

`.github/workflows/link-checker.yml` runs lychee over the built site on PRs, every
Monday and by hand.

## Special Features

### 3D Panorama View
Located in `/pohled3d/` directory:
- Interactive 360° view of the coworking space
- Uses Pano2VR player
- Accessible via separate HTML files

### Responsive Design
- Mobile-first Bootstrap grid system
- Animated navigation header that shrinks on scroll
- Smooth scrolling to page sections
- Modal dialogs for enlarged images

### SEO Features
- RSS feed (`feed.xml`)
- Semantic HTML structure
- Meta descriptions in `_config.yml`
- Custom permalinks (pretty URLs)

## Content Management

### Adding/Editing Team Members
Edit the `people` array in `_config.yml`:
```yaml
people:
- name: Member Name
  pic: 1  # Corresponds to img/team/1.jpg
  position: Job description
  social:
    - title: icon-name  # Font Awesome icon
      url: profile-url
```

### Updating Pricing
Modify the `price` array in `_config.yml`:
```yaml
price:
- tariff: Price text
  pic: icon-name  # Font Awesome icon
  desc-title: Title
  desc: Description
```

### Adding Equipment/Facilities
Update the `history` array in `_config.yml`:
```yaml
history:
- title: Feature name
  pic: image-name  # Corresponds to img/about/image-name.jpg
  descr: Description
```

### Adding Photos to Gallery
The photo gallery uses Jekyll posts in the `_posts/` directory:
1. Add thumbnail image to `img/portfolio/X-thumbnail.jpg`
2. Add full-size image to `img/portfolio/X.jpg`
3. Create a new post file in `_posts/` with format `YYYY-MM-DD-project-X.markdown`:
```markdown
---
title: Photo Title
subtitle: Photo Description
layout: default
modal-id: X
img: X.jpg
thumbnail: X-thumbnail.jpg
---
```

## Continuous Integration & Deployment

See **Deployment** above (`.github/workflows/deploy.yml`, `link-checker.yml`, and the
Claude workflows `claude.yml` / `claude-code-review.yml`).

### Gemfile Dependencies
```ruby
gem 'github-pages'  # GitHub Pages compatible Jekyll
gem 'html-proofer'  # HTML validation tool
```

## Key Files Reference

### Configuration
- `_config.yml` - All site settings and content data
- `.ruby-version` - Ruby version specification (3.3.6)
- `Gemfile` - Ruby gem dependencies (github-pages, html-proofer)
- `Gemfile.lock` - Locked dependency versions
- `wrangler.jsonc` - Cloudflare Worker config (custom domains, `_site/`)
- `.github/workflows/deploy.yml` - build, deploy, PR previews and checks

### Templates
- `_layouts/default.html` - Main page template
- `index.html` - Home page using default layout

### Stylesheets
- `style.css` - Main custom styles
- `_layouts/style.css` - Additional layout styles
- `_includes/css/agency.css` - Agency theme styles
- `_includes/css/bootstrap.min.css` - Bootstrap framework

### Scripts
- `js/agency.js` - Main site JavaScript
- `js/cbpAnimatedHeader.js` - Animated header functionality
- `js/map.js` - Google Maps configuration

### Data and Plugins
- `_data/template.yml` - Template data for Jekyll
- `_plugins/hex_to_rgb.rb` - Custom Jekyll plugin for color conversion
- `_posts/` - Portfolio/gallery posts (markdown files with front matter)

## Browser Support

The site uses Bootstrap 3.x and jQuery 1.x, supporting:
- Modern browsers (Chrome, Firefox, Safari, Edge)
- IE 9+
- Mobile browsers (iOS Safari, Chrome Mobile)

## Contact & Social Media

- **Website**: http://www.cowosedlice.cz/
- **Phone**: Radim Klaška at +420 605 271 780
- **Email**: radim@cowosedlice.cz
- **Facebook**: https://www.facebook.com/cowosedlice/
- **GitHub**: https://github.com/cowosedlice
- **Address**: Míru 218, Novosedlice, 417 31

## License

See LICENSE file in repository root.

## Contributing

1. Fork the repository
2. Create a feature branch from `main`
3. Make your changes
4. Test locally with `bundle exec jekyll serve`
5. Submit a pull request to the `main` branch
6. GitHub Actions will automatically build and test your PR
7. Once approved and merged, changes will be automatically deployed to https://cowosedlice.cz (Cloudflare)

## Notes for AI Assistants

### Project Type
This is a **static Jekyll website** for a coworking space, not a web application with backend logic.

### Key Understanding
- Content is primarily managed through `_config.yml`
- Layout is modular with includes in `_includes/`
- Images are organized by purpose in `img/` subdirectories
- Czech language throughout (variable names may be English)

### Common Tasks
- **Update member info**: Edit `_config.yml` → `people` array
- **Change pricing**: Edit `_config.yml` → `price` array
- **Add facilities**: Edit `_config.yml` → `history` array
- **Modify styles**: Edit `style.css` or `_includes/css/agency.css`
- **Change layout**: Edit files in `_includes/` or `_layouts/`

### Testing Changes
Always run `bundle exec jekyll serve` to preview changes locally before committing.
