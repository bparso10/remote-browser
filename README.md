# RemNote Browser Plugin

A RemNote plugin that embeds a functional web browser inside the RemNote desktop app.

## Features

- 🌐 Embedded browser pane with full navigation controls
- 🔍 Launch browser from any rem via `/browse` slash command
- ↔️ Resizable and draggable browser windows
- 🔒 Security through sandboxed iframes and URL validation
- 📜 Browser history tracking
- ⌨️ Keyboard shortcut support (Ctrl+Shift+B)

## Installation

1. Build the plugin:
   ```bash
   npm install
   npm run build
   ```

2. Load the plugin in RemNote:
   - Open RemNote **desktop app** (not web version)
   - Go to Settings → Plugins
   - Enable "Developer mode" if needed
   - Click "Load unpacked plugin"
   - Select the **entire project directory** (not just dist/)
   - The plugin should appear in your plugins list

## Development Preview

To preview the browser widget during development:

```bash
npm run preview
```

Then open http://localhost:8080 in your browser. 

**Note:** This is only for development preview. The plugin must be loaded in RemNote Desktop to work properly with slash commands and keyboard shortcuts.

## Usage

### Opening the Browser

1. **Slash Command**: Type `/browse` in any rem to open the browser pane
2. **Keyboard Shortcut**: Press `Ctrl+Shift+B` (or `Cmd+Shift+B` on Mac)
3. **Browse Selected Text**: Select text and use `/browse-selection` to search for it

### Browser Controls

- **Back/Forward**: Navigate through your browsing history
- **Refresh**: Reload the current page
- **URL Bar**: Enter any URL and press Enter or click Go
- **Close**: Click the X button to close the browser pane

## Security

The plugin implements several security measures:
- All web content is loaded in sandboxed iframes
- URL validation before loading
- Content Security Policy (CSP) headers
- No credential storage

## Development

```bash
# Install dependencies
npm install

# Development mode with hot reload
npm run dev

# Build for production
npm run build

# Type checking
npm run type-check

# Clean build artifacts
npm run clean
```

## Architecture

- **RemNote Plugin SDK**: For widget registration and commands
- **React 17 + TypeScript**: UI components (uses React 17 for SDK compatibility)
- **Sandboxed iframes**: Secure web content display
- **Local storage**: Browser history persistence

## Limitations

- Some websites block iframe embedding (e.g., Google, Facebook)
- No access to browser cookies or local storage
- Limited to HTTPS/HTTP protocols
- No browser extensions or plugins

## Publishing

See [PUBLISHING.md](PUBLISHING.md) for detailed instructions on how to build and upload this plugin to the RemNote marketplace.

## License

MIT