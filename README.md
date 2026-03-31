# FSA Launchpad 11ty

A minimal, accessible static site for FSA documentation built with [Eleventy](https://www.11ty.dev/), the [U.S. Web Design System](https://designsystem.digital.gov/), and [Netlify CMS](https://www.netlifycms.org/) for content management.


## Quick Start

### Local Development

1. **Clone and install**

   ```bash
   git clone <repository-url>
   cd uswds-starter-site
   npm install
   ```

2. **Start the development server**

   ```bash
   npm start
   ```

3. **View the site**

   Open your browser to `http://localhost:8080`

### Available Scripts

- `npm start` - Run development server with hot reload
- `npm run build` - Build production site to `_site/` directory  
- `npm run clean` - Remove `_site/` directory
- `npm run cms:proxy` - Run Netlify CMS proxy server (for local CMS)
- `npm run dev` - Run both Eleventy and CMS proxy together

## Font Loading

This starter uses **USWDS fonts hosted locally** - fonts are copied from the `@uswds/uswds` package to your build folder automatically.

Fonts are automatically copied from `node_modules/@uswds/uswds/dist/fonts/` to `_site/assets/fonts/` during build.

### Local CMS Development

To test Netlify CMS locally:

**Quick method** (recommended):
```bash
# 1. Uncomment local_backend: true in admin/config.yml
# 2. Run both servers at once:
npm run dev
```

**Manual method**:
```bash
# Terminal 1
npm start

# Terminal 2
npm run cms:proxy
```

Access CMS at `http://localhost:8080/admin/`

## Customization

### Changing Colors

Edit `styles/custom/_overrides.scss` to modify the color scheme:

```scss
.hero {
  background-color: #0D4F8B; // Change hero background
}
```

### Adding New Sections

1. **Create a new folder** in `src/` (e.g., `src/resources/`)
2. **Add `index.md`** with section layout:
   ```yaml
   ---
   layout: section
   title: Resources
   section: resources
   description: Helpful resources and documentation
   ---
   ```
3. **Update navigation** in `src/_layouts/default.njk`
4. **Add collection** to `admin/config.yml` for CMS management

### Adding New Post Types

1. **Create folder structure** in `src/`
2. **Create posts** with appropriate front matter
3. **Add to Netlify CMS config** in `admin/config.yml`


## Credits

Built with:
- [Eleventy](https://www.11ty.dev/) - Static site generator
- [USWDS](https://designsystem.digital.gov/) - U.S. Web Design System
- [Netlify CMS](https://www.netlifycms.org/) - Content management
- Inspired by [TTS Handbook](https://handbook.tts.gsa.gov/)
