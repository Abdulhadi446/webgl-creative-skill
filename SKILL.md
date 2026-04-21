---
name: WebGL Creative Experience
description: This skill should be used when the user asks to "build a creative agency website", "create immersive WebGL experience", "build award-winning portfolio site", "create full-screen 3D canvas website", "edit the activetheory site", "modify the WebGL site", or wants to create high-end creative digital experiences similar to Active Theory.
version: 0.2.0
---

# WebGL Creative Experience Development

Create premium, immersive creative agency websites using WebGL technology by cloning and modifying an existing Active Theory-style codebase.

## Workflow

### Step 1: Clone Base Repository

Clone the WebGL starter template:
```bash
git clone https://github.com/Abdulhadi446/activetheory.net.git
cd activetheory.net
```

This provides a complete working WebGL application with:
- Full-screen WebGL canvas
- Hydra WebGL framework
- Custom shader system
- 3D geometry pipeline
- KTX2/Basis texture compression
- PBR rendering
- Audio/video integration
- Mobile optimization

### Step 2: Understand the Structure

The cloned repo contains:

```
activetheory.net/
├── index.html              # Entry point with feature detection
├── unsupported.html       # Fallback for old browsers
├── robots.txt
├── assets/
│   ├── css/               # Stylesheets
│   ├── data/               # UIL JSON (camera/scene config)
│   ├── fonts/             # NBArchitekt font family
│   ├── geometry/          # Binary 3D models
│   ├── images/            # Textures (KTX2, PNG)
│   ├── js/
│   │   ├── app.xxxx.js    # Main bundle (1.8MB minified)
│   │   ├── hydra/         # WebGL framework
│   │   └── lib/           # basis_transcoder, draco
│   ├── shaders/           # GLSL shaders (compiled.vs)
│   ├── music/             # Audio tracks
│   └── video/             # Showreel
```

### Step 3: Modify Based on User Request

Common modifications:

#### Change Text/Content
- Edit `assets/data/uil.json` for UI text and positions
- Modify `index.html` title and meta tags

#### Change Images/Textures
- Replace files in `assets/images/`
- Use KTX2 format for optimal performance

#### Change 3D Models
- Replace geometry in `assets/geometry/`
- Use GLB format or Draco-compressed binary

#### Change Colors/Styles
- Modify shaders in `assets/shaders/compiled.vs`
- Edit `index.html` inline CSS

#### Change Audio/Video
- Replace files in `assets/music/` or `assets/video/`

#### Change Fonts
- Replace font files in `assets/fonts/`
- Update font-face declarations in `index.html`

### Step 4: Test Changes

Serve locally and test:
```bash
cd activetheory.net
python3 -m http.server 8000
# or
npx serve .
```

Open http://localhost:8000 in browser.

## Key Technical Details

### Browser Detection
```javascript
// Tests optional chaining support
try{eval("let obj = {}; obj?.prop")}catch(e){
    window.location.replace("unsupported.html");
}
```

### Cache Busting
```javascript
window._CACHE_="1746999829739"; // Build timestamp
var s="assets/js/app."+window._CACHE_+".js";
```

### Full-Screen Canvas CSS
```css
#Stage,body,html{width:100%;height:100%;overflow:hidden;touch-action:none;background:#000}
```

### Mobile Optimization
- `viewport-fit=cover` - Full screen on iOS
- `touch-action:none` - Disable touch gestures
- `user-select:none` - Prevent text selection
- `-webkit-tap-highlight-color:transparent` - Hide tap highlight

### Texture Format
- Use KTX2 with Basis Universal compression
- Transcode with `basis_transcoder.js` + `.wasm`

### Shader System
Shaders stored in `compiled.vs` with custom delimiter:
```glsl
{@}shader_name{@}
// shader code here
```

Includes blend modes, noise functions, PBR lighting.

## Standards

### DO:

- Clone existing repo as starting point
- Use KTX2/Basis for textures
- Keep full-screen WebGL approach
- Maintain mobile optimization
- Use custom distinctive fonts

### DON'T:

- Replace WebGL with DOM-based layout
- Use generic Bootstrap/Tailwind
- Switch to standard scrolling
- Use uncompressed textures
