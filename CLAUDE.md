# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Overview

This repository contains the main Jekyll site for maitriser.ca, which serves as a portal to French translations of technical cryptocurrency books including "Maîtriser Bitcoin", "Maîtriser Ethereum", and "Maîtriser le Réseau Lightning". The translations use Quebec French terminology from the Grand dictionnaire terminologique (GDT).

## Common Development Commands

### Jekyll Site Development
```bash
# Install Jekyll dependencies (run from docs/ directory)
cd docs/
bundle install

# Serve Jekyll site locally
bundle exec jekyll serve

# Build Jekyll site
bundle exec jekyll build
```

### Ruby Environment
```bash
# Install Ruby dependencies (from project root or docs/ directory)
bundle install
```

## Architecture

### Site Structure
- **Main Site**: www.maitriser.ca (this repository - maitriser-ca.github.io)
- **Bitcoin Book**: bitcoin.maitriser.ca 
- **Ethereum Book**: ethereum.maitriser.ca
- **Lightning Network Book**: lightning.maitriser.ca
- **Computer Science Docs**: informatique.maitriser.ca

### Jekyll Configuration
- **Theme**: Minima (Jekyll's default theme)
- **Plugins**: jekyll-feed, jekyll-seo-tag
- **Deployment**: GitHub Pages from `/docs/` directory
- **Custom Styles**: Located in `_sass/minima/` directory with custom overrides
- **Assets**: Images and banners stored in `/docs/assets/`

### Content Organization
```
/docs/
├── _config.yml          # Jekyll configuration
├── _layouts/            # Custom page layouts
├── _includes/           # Reusable components
├── _sass/               # Custom Sass styling
├── assets/              # Images, CSS, and static files
├── index.markdown       # Homepage content
├── about.markdown       # About page
└── Gemfile             # Ruby dependencies
```

### Domain Architecture
The main site acts as a portal linking to separate GitHub repositories for each book:
- Each book maintains its own repository with AsciiDoc source files
- This site provides navigation and overview of all available resources
- All sites use consistent branding and Quebec French terminology

### Styling System
- Base theme: Minima with classic skin
- Custom variables: `_sass/minima/custom-variables.scss`
- Custom styles: `_sass/minima/custom-styles.scss`
- Main stylesheet: `assets/css/style.scss`

### Content Guidelines
- Homepage content in `index.markdown` showcases all available books
- About page provides author information and site details
- All content written in Quebec French following GDT terminology
- Book banners and promotional images stored in `/assets/`

## Troubleshooting

### Ruby 3.3 Compatibility
If you encounter `undefined method '[]' for nil` errors with Jekyll 4.2.2 and Ruby 3.3:
1. Update Jekyll to 4.3.0+ in Gemfile: `gem "jekyll", "~> 4.3.0"`
2. Update webrick to 1.7+ in Gemfile: `gem "webrick", "~> 1.7"`
3. Run `bundle update` to resolve dependencies

### Sass Deprecation Warnings
Sass @import deprecation warnings are expected with current Minima theme and don't affect functionality.