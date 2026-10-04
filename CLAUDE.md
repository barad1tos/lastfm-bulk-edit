# Last.fm Bulk Edit Userscript - CLAUDE.md

## Project Overview

This is a TypeScript-based userscript for bulk editing Last.fm scrobbles. It provides functionality to edit multiple scrobbles at once through a modal interface on the Last.fm website.

**Key Features:**
- Bulk edit artists, albums, and track names
- Automatic edits management
- Modal-based UI integrated into Last.fm pages
- Requires Last.fm Pro subscription for full functionality

## Build System

### Primary Commands
- `npm run build` - Production build (minified)
- `npm run build-development` - Development build with source maps and watch mode
- `npm run lint` - ESLint code quality checks

### Build Process
- **Input**: TypeScript source files in `src/`
- **Output**: Compiled userscript at `dist/lastfm-bulk-edit.user.js`
- **Bundler**: Webpack 5 with UserscriptPlugin
- **Target**: ES2018 for broad browser compatibility

## Architecture

### Technology Stack
- **Language**: TypeScript
- **Build Tool**: Webpack 5 with UserscriptPlugin
- **Code Quality**: ESLint with TypeScript support
- **Dependencies**: async-mutex, he, tiny-async-pool

### Project Structure
```
src/                    # TypeScript source files
dist/                   # Compiled userscript output
webpack.config.js       # Webpack configuration
tsconfig.json          # TypeScript configuration
.eslintrc.js           # ESLint rules
package.json           # Dependencies and scripts
```

### Key Components
- **Modal System**: UI overlay for bulk editing interface
- **API Integration**: Last.fm API calls for reading/writing scrobble data
- **Bulk Operations**: Utilities for processing multiple scrobbles
- **Automatic Edits**: Management of predefined edit rules

## Development Workflow

### Getting Started
1. Install dependencies: `npm install`
2. Development build: `npm run build-development`
3. Install userscript in browser extension (Tampermonkey/Violentmonkey)
4. Navigate to Last.fm to test functionality

### File Modification Protocol
**MANDATORY**: After every file edit/modification:
1. Run `trunk check [modified-file-path]` to validate changes
2. If errors found, fix them iteratively using trunk's suggestions
3. Re-run `trunk check` until all errors are resolved
4. Only proceed to next task when validation passes
5. For unusual/non-typical trunk errors, consult with user before proceeding

**IMPORTANT NOTE**: Do NOT attempt to fix Sourcery issues in the compiled `dist/lastfm-bulk-edit.user.js` file. This is a webpack-compiled output file containing auto-generated code. Sourcery warnings in compiled files are expected and should be ignored. Focus on source files in `src/` directory instead.

### Code Quality & Validation
- ESLint configured for TypeScript
- Sourcery integration for additional code quality checks
- Custom rules for consistent formatting and best practices
- **IMPORTANT**: After each file modification, run `trunk check [file]` to validate changes
- Fix any trunk errors iteratively before proceeding
- For non-typical errors, ask the user for guidance on resolution approach

### Build Artifacts
- Main output: `dist/lastfm-bulk-edit.user.js`
- Development builds include source maps for debugging
- Production builds are minified and optimized

## Configuration Notes

### Webpack Configuration
- Uses UserscriptPlugin for proper userscript headers
- External dependency on 'he' library (HTML entity encoding)
- Development mode includes watch functionality

### TypeScript Configuration
- Extends recommended TypeScript settings
- Target ES2018 for compatibility
- Source maps enabled for debugging

### ESLint Configuration
- TypeScript-aware linting
- Custom rules for code style consistency
- Configured for userscript development patterns

## Dependencies

### Runtime Dependencies
- `async-mutex`: Concurrency control for API calls
- `he`: HTML entity encoding/decoding
- `tiny-async-pool`: Pool management for async operations

### Development Dependencies
- TypeScript compiler and tooling
- Webpack and UserscriptPlugin
- ESLint with TypeScript support

## Usage Context

This userscript runs in the browser on Last.fm pages, providing additional functionality for users with Last.fm Pro subscriptions. It integrates seamlessly with the existing Last.fm interface while adding powerful bulk editing capabilities.