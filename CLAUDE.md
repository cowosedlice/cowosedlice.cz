# CLAUDE.md - Cowosedlice.cz Project Documentation

## Project Overview

**Cowosedlice.cz** is a Jekyll-based static website for a coworking space located in Novosedlice near Teplice, Czech Republic. The site serves as the primary online presence for this shared office space, showcasing facilities, pricing, member profiles, and contact information.

**Domain:** www.cowosedlice.cz
**Repository:** github.com/cowosedlice/cowosedlice.cz
**Technology:** Jekyll static site generator hosted on GitHub Pages
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
- **GitHub Pages** - Hosting platform
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
│   └── default.html         # Main layout template
├── _includes/               # Reusable HTML components
│   ├── header.html          # Navigation and hero section
│   ├── team.html            # Active members section
│   ├── portfolio_grid.html  # Photo gallery
│   ├── about.html           # Equipment/facilities section
│   ├── map.html             # Location map
│   ├── price.html           # Pricing table
│   ├── contact.html         # Contact form
│   ├── footer.html          # Footer with social links
│   ├── modals.html          # Modal dialogs
│   ├── js.html              # JavaScript includes
│   ├── head.html            # HTML head section
│   └── css/                 # CSS partials
│       ├── agency.css       # Custom styles
│       ├── bootstrap.min.css
│       └── map.css
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
├── index.html               # Home page
├── style.css                # Main stylesheet
├── feed.xml                 # RSS feed
├── favicon.ico              # Site favicon
├── CNAME                    # Custom domain configuration
├── Gemfile                  # Ruby dependencies
├── Gemfile.lock             # Locked dependency versions
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
- Radek Novák (webgames.cz - PHP, Nette, JavaScript, MySQL, SEO)
- Radim Klaška (Drupal developer for Morpht Pty. Ltd.)
- Honza Pára (Drupal developer, site builder)
- Jan Nedvěd (Steel construction designer)
- Available slots (showing open positions)

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
- **Daily rate**: 210 Kč per day (2 free trial days for new members)
- **Medium plan**: 1540 Kč/month (10 working days, 8:00-17:00, flexible seating)
- **Large plan**: 2450 Kč/month (24/7 access, dedicated workspace)

All plans include: WiFi, printer, PC, kitchen, fridge, coffee maker, etc.

### 8. Contact Section (`_includes/contact.html`)
Contact form and information:
- Email: radek@cowosedlice.cz
- Social media links (Facebook, GitHub)

### 9. Footer (`_includes/footer.html`)
Social media links and copyright information.

## Configuration

The `_config.yml` file contains all site configuration and content:

```yaml
url: http://www.cowosedlice.cz
title: Cowosedlice.cz - sdílená kancelář v Novosedlicích u Teplic
email: radek@cowosedlice.cz
description: "Cowosedlice jsou tu pro ty, kterým nevyhovuje práce z domova..."

# Content sections are configured with YAML data structures
history: # Equipment list
price: # Pricing tiers
people: # Team members
social: # Social media links
address: # Physical address
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

The site uses GitHub Pages for automatic deployment:
- **Production branch**: `gh-pages`
- **Development branch**: `dev`
- **Travis CI**: Automated builds configured for both branches

Push to `gh-pages` branch to deploy to production.

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
1. Add thumbnail image to `img/photos/X-thumbnail.jpg`
2. Add full-size image to `img/photos/X.jpg`
3. Update portfolio data in Jekyll front matter or includes

## Continuous Integration

Build status badges in README.md:
- Development branch: [![Build Status](https://travis-ci.org/cowosedlice/cowosedlice.cz.svg?branch=dev)](https://travis-ci.org/cowosedlice/cowosedlice.cz)
- Production branch: [![Build Status](https://travis-ci.org/cowosedlice/cowosedlice.cz.svg?branch=gh-pages)](https://travis-ci.org/cowosedlice/cowosedlice.cz)

## Key Files Reference

### Configuration
- `_config.yml` - All site settings and content data
- `Gemfile` - Ruby gem dependencies
- `CNAME` - Custom domain configuration

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

## Browser Support

The site uses Bootstrap 3.x and jQuery 1.x, supporting:
- Modern browsers (Chrome, Firefox, Safari, Edge)
- IE 9+
- Mobile browsers (iOS Safari, Chrome Mobile)

## Contact & Social Media

- **Website**: http://www.cowosedlice.cz/
- **Facebook**: https://www.facebook.com/cowosedlice/
- **GitHub**: https://github.com/cowosedlice
- **Email**: radek@cowosedlice.cz

## License

See LICENSE file in repository root.

## Contributing

1. Fork the repository
2. Create a feature branch from `dev`
3. Make your changes
4. Test locally with `bundle exec jekyll serve`
5. Submit a pull request to the `dev` branch

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
