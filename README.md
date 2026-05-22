# Maximo Application Configuration - Local Dev Mode

A GitHub Pages site for the Maximo Developer Configuration Tools VSCode extension.

🌐 **Live Site:** https://ibm-mas.github.io/maf-local-dev-mode/

## Overview

This repository hosts the documentation and installation resources for the Maximo Application Configuration - Local Dev Mode VSCode extension. The site provides:

- **Quick Installation**: One-line curl command for automated setup
- **Manual Installation**: Step-by-step VSIX installation guide
- **Features Documentation**: Comprehensive feature showcase
- **OIDC Setup**: Authentication configuration for remote MAS environments
- **Helper Scripts**: Automated tools for installation and OIDC setup

## Site Structure

```
docs/
├── index.html              # Landing page with quick start
├── install.html            # Installation guide
├── features.html           # Feature documentation
├── oidc.html              # OIDC configuration guide
├── manual.html            # Manual installation fallback
├── css/
│   ├── main.css           # Core styles (IBM Bob-inspired)
│   └── responsive.css     # Responsive design
├── js/
│   └── main.js            # Interactive features
└── scripts/
    ├── install.sh         # Automated installer
    ├── oidc.sh           # OIDC setup wizard
    └── get-credentials.sh # OpenShift credential retrieval
```

## Local Development

### Prerequisites

- Node.js 20.0.0 or higher (for testing scripts)
- A web browser
- Optional: Python 3 for local server

### Running Locally

1. Clone the repository:
   ```bash
   git clone https://github.com/ibm-mas/maf-local-dev-mode.git
   cd maf-local-dev-mode
   ```

2. Serve the docs folder:
   ```bash
   # Using Python 3
   cd docs
   python3 -m http.server 8000
   
   # Or using Node.js
   npx serve docs
   ```

3. Open http://localhost:8000 in your browser

### Testing Scripts

Before deploying, test the installation and OIDC scripts:

```bash
# Test install script (dry run)
bash docs/scripts/install.sh --help

# Test OIDC script
bash docs/scripts/oidc.sh --help

# Test credential retrieval (requires OpenShift access)
bash docs/scripts/get-credentials.sh --help
```

## Deployment

### GitHub Pages Setup

1. **Enable GitHub Pages:**
   - Go to repository Settings → Pages
   - Source: Deploy from a branch
   - Branch: `main`
   - Folder: `/docs`
   - Save

2. **Verify Deployment:**
   - Wait 1-2 minutes for build
   - Visit: https://ibm-mas.github.io/maf-local-dev-mode/

### Custom Domain (Optional)

To use a custom domain:

1. Add a `CNAME` file to `/docs`:
   ```bash
   echo "your-domain.com" > docs/CNAME
   ```

2. Configure DNS:
   - Add CNAME record pointing to `ibm-mas.github.io`
   - Or A records pointing to GitHub Pages IPs

3. Enable HTTPS in repository settings

## Design System

The site uses an IBM Bob-inspired design system:

### Colors
- **Background:** `#161616` (dark), `#262626` (alt)
- **Primary:** `#4589ff` (IBM Blue)
- **Text:** `#f4f4f4` (white), `#c6c6c6` (gray)
- **Accent:** `#0f62fe` (hover), `#78a9ff` (light)

### Typography
- **Font Family:** IBM Plex Sans, IBM Plex Mono
- **Headings:** 600-700 weight
- **Body:** 400 weight
- **Code:** IBM Plex Mono

### Components
- Responsive navigation with mobile menu
- Feature cards with hover effects
- Code blocks with copy-to-clipboard
- Info boxes (blue, green, yellow)
- Step-by-step guides
- CTA sections

## Contributing

### Adding New Pages

1. Create HTML file in `/docs`
2. Use existing pages as templates
3. Update navigation in all pages
4. Add to footer links
5. Test responsive design

### Updating Styles

1. Edit `/docs/css/main.css` for core styles
2. Edit `/docs/css/responsive.css` for breakpoints
3. Test on mobile, tablet, and desktop
4. Verify accessibility (WCAG AA)

### Updating Scripts

1. Edit scripts in `/docs/scripts/`
2. Test locally before committing
3. Update documentation if behavior changes
4. Ensure error handling is robust

## Maintenance

### Regular Updates

- **Extension Releases:** Update version numbers and download links
- **Dependencies:** Keep Node.js requirements current
- **Security:** Review and update authentication methods
- **Content:** Keep feature documentation in sync with extension

### Monitoring

- Check GitHub Pages build status
- Monitor 404 errors in repository insights
- Review user feedback in GitHub Issues
- Test installation scripts periodically

## Support

- **Documentation:** https://ibm-mas.github.io/maf-local-dev-mode/
- **Issues:** https://github.com/ibm-mas/maf-local-dev-mode/issues
- **Discussions:** https://github.com/ibm-mas/maf-local-dev-mode/discussions

## License

Apache 2.0 - See LICENSE file for details

## Acknowledgments

- Design inspired by [IBM Bob](https://bob.ibm.com/)
- Built with IBM Plex fonts
- Powered by GitHub Pages