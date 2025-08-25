# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Hugo static site using the Ananke theme for "Fallon Events". The site uses Hugo modules to manage the Ananke theme dependency.

## Development Commands

### Local Development
```bash
hugo server
```
Starts local development server at http://localhost:1313

### Build
```bash
hugo --minify
```
Builds the site to the `public/` directory with minification

### Module Management
```bash
hugo mod get github.com/theNewDynamic/gohugo-theme-ananke@master
hugo mod tidy
```
Updates theme module and cleans dependencies

## Architecture

### Hugo Configuration
- Main config: `config/_default/hugo.toml` (title, theme module import)
- Additional config: `config.toml` (minimal - just unsafe = true)
- Uses Hugo modules with minimum version 0.128.0
- Theme: `github.com/theNewDynamic/gohugo-theme-ananke` imported as module

### Content Structure
- Posts: `content/posts/` - Blog posts and articles
- Static assets: `static/images/` - Images and other static files
- Generated content: `public/` - Built site output (do not edit directly)
- Resources: `resources/_gen/` - Hugo-generated resources cache

### Theme System
- Uses Ananke theme via Hugo modules (not Git submodule)
- Tachyons CSS utility framework for styling
- Featured image: `/static/images/cover.jpg` set globally
- Supports custom CSS via `assets/ananke/css/` directory

### Key Files
- `archetypes/default.md` - Template for new content
- `netlify.toml` - Netlify deployment configuration
- Content in markdown format with front matter configuration