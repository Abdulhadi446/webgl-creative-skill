---
name: WebGL Creative Experience
description: This skill should be used when the user asks to "build a creative agency website", "create immersive WebGL experience", "build award-winning portfolio site", "create full-screen 3D canvas website", or wants to create high-end creative digital experiences similar to Active Theory.
version: 0.1.0
---

# WebGL Creative Experience Development

Create premium, immersive creative agency websites using WebGL technology.

## Core Architecture

Build a single-page application with full-screen WebGL canvas as the primary rendering surface, not DOM-based HTML/CSS layouts.

### Project Structure

```
project/
├── index.html
├── unsupported.html
├── robots.txt
├── assets/
│   ├── css/              stylesheets
│   ├── data/              JSON data files
│   ├── fonts/             web fonts (woff2, woff, otf)
│   ├── geometry/          3D models (.glb, .gltf)
│   ├── images/           textures and assets
│   ├── js/
│   │   ├── app.xxxx.js   main application bundle
│   │   ├── hydra/         WebGL framework
│   │   └── lib/           libraries (draco, basis)
│   ├── shaders/          GLSL vertex/fragment shaders
│   ├── music/            audio files
│   └── video/            video assets
│   └── meta/             favicons, manifest
```

## Required Components

### index.html

Create HTML with:

1. **Viewport meta** - Full viewport, disable scaling
   ```html
   <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no, minimal-ui, viewport-fit=cover">
   ```

2. **Preload custom fonts** - Inline critical fonts
   ```css
   @font-face{font-family:"CustomFont";src:url(assets/fonts/path.woff2)format("woff2")...}
   ```

3. **Base styling** - Full-screen canvas
   ```css
   #Stage,body,html{width:100%;height:100%;overflow:hidden;touch-action:none;background:#000}
   ```

4. **Load main JS** - Cache-busted bundle
   ```javascript
   window._CACHE_="timestamp";
   var s="assets/js/app."+window._CACHE_+".js";
   ```

5. **Unsupported browser detection** - Test optional chaining
   ```javascript
   try{eval("let obj = {}; obj?.prop")}catch(e){window.location.replace(window._UNSUPPORTED_PAGE_);}
   ```

6. **Google Analytics** - GTM setup in head

### WebGL Framework

Implement a WebGL rendering framework with:

1. **Canvas management** - Create and manage WebGL context
2. **Shader compilation** - Load and compile GLSL shaders
3. **Geometry handling** - Load 3D models (GLTF/GLB)
4. **Texture loading** - Support basis compressed textures
5. **Animation loop** - RequestAnimationFrame based loop
6. **Camera controls** - Perspective camera with controls
7. **Post-processing** - Effects pipeline

### Performance Features

1. **Disable default scroll** - Lock to viewport with `overflow:hidden`
2. **Touch handling** - Disable zoom with `touch-action:none`
3. **iOS-specific fixes** - Handle Safari quirks
4. **Preload critical assets** - Use `<link rel="preload">`
5. **Code splitting** - Separate vendor libraries

## Essential Features

### 1. Full-Screen Experience
- No traditional scrolling
- Custom scroll navigation
- Smooth page transitions
- Lock viewport dimensions

### 2. Custom Typography
- Use distinctive fonts (not generic Google Fonts)
- Self-host font files (woff2 + woff + otf)
- Preload critical font weights

### 3. Audio/Video Integration
- Background music playback
- Video texture support
- Audio controls

### 4. Mobile Optimization
- Touch-friendly interactions
- Viewport-fit=cover
- Disable text selection
- Hide tap highlight

### 5. PWA Support
- Web app manifest
- Service worker for offline
- Apple touch icon
- Theme color meta

## Development Workflow

### Step 1: Set Up Project

Create directory structure with all required folders.

### Step 2: Create Base HTML

Build index.html with:
- SEO meta tags (canonical, OG, Twitter)
- Critical CSS inlined
- Font preloading
- JS bundle loading
- Analytics setup

### Step 3: Develop WebGL Core

Build the rendering system:
- Canvas initialization
- Shader loader
- Geometry processor
- Texture handler

### Step 4: Add Features

Implement:
- Navigation system
- Page transitions
- Audio player
- Video backgrounds

### Step 5: Optimize

Add performance:
- Bundle and minify JS
- Compress textures
- Preload assets
- Cache-busting

## Standards

### DO:

- Use distinctive, custom typography
- Create immersive full-screen experiences
- Implement smooth animations
- Add touch gesture support
- Include unsupported browser fallback
- Set up proper SEO meta

### DON'T:

- Use generic Bootstrap/Tailwind layouts
- Create box-model CSS layouts
- Use standard scrolling behavior
- Rely on DOM for primary content
- Use generic Google Fonts