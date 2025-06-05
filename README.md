# three.js

[![NPM Package][npm]][npm-url]
[![Build Size][build-size]][build-size-url]
[![NPM Downloads][npm-downloads]][npmtrends-url]
[![Discord][discord]][discord-url]
[![DeepWiki][deepwiki]][deepwiki-url]

## JavaScript 3D Library

**Three.js** is a cross-browser JavaScript library and application programming interface (API) used to create and display animated 3D computer graphics in a web browser using WebGL. The source code is hosted in a repository on GitHub.

### ✨ Features

- 🎨 **Renderers**: WebGL, WebGPU, SVG, and CSS3D renderers
- 📦 **Scenes**: Efficient scene graph with automatic frustum culling
- 📷 **Cameras**: Perspective and orthographic cameras
- 🎬 **Animation**: Armatures, forward kinematics, inverse kinematics, morph, and keyframe
- 💡 **Lights**: Ambient, directional, point, spot, and hemisphere lights
- 🎭 **Materials**: Standard, physical, toon, and more with fog support
- 🔷 **Geometries**: Plane, cube, sphere, torus, 3D text, and more
- 🧩 **Shaders**: Access to full OpenGL Shading Language (GLSL) capabilities
- 🎛️ **Objects**: Meshes, particles, sprites, lines, ribbons, bones, and more
- 📊 **Data loaders**: Binary, image, JSON, and scene formats
- 🔧 **Utilities**: Full set of time and 3D math functions including frustum, matrix, quaternion, and more
- 🎮 **Input**: Mouse and touch support
- 🥽 **Virtual Reality**: WebXR support for VR and AR experiences
- 📱 **Examples**: Over 150 files of coding examples plus fonts, models, textures, sounds, and other support files

### 📚 Resources

[Examples](https://threejs.org/examples/) &mdash;
[Documentation](https://threejs.org/docs/) &mdash;
[Manual](https://threejs.org/manual/) &mdash;
[Wiki](https://github.com/mrdoob/three.js/wiki) &mdash;
[Migration Guide](https://github.com/mrdoob/three.js/wiki/Migration-Guide) &mdash;
[Forum](https://discourse.threejs.org/) &mdash;
[Discord](https://discord.gg/56GBJwAnUS) &mdash;
[Stack Overflow](https://stackoverflow.com/questions/tagged/three.js)

### 🚀 Quick Start

#### Installation

**NPM**

```bash
npm install three
```

**YARN**

```bash
yarn add three
```

**CDN**

```html
<script type="importmap">
  {
    "imports": {
      "three": "https://cdn.jsdelivr.net/npm/three@0.177.0/build/three.module.js",
      "three/addons/": "https://cdn.jsdelivr.net/npm/three@0.177.0/examples/jsm/"
    }
  }
</script>
```

#### Basic Usage

This code creates a scene, a camera, and a geometric cube, and it adds the cube to the scene. It then creates a `WebGL` renderer for the scene and camera, and it adds that viewport to the `document.body` element. Finally, it animates the cube within the scene for the camera.

```javascript
import * as THREE from 'three';

const width = window.innerWidth, height = window.innerHeight;

// Create camera
const camera = new THREE.PerspectiveCamera( 70, width / height, 0.01, 10 );
camera.position.z = 1;

// Create scene
const scene = new THREE.Scene();

// Create a cube
const geometry = new THREE.BoxGeometry( 0.2, 0.2, 0.2 );
const material = new THREE.MeshNormalMaterial();
const mesh = new THREE.Mesh( geometry, material );
scene.add( mesh );

// Create renderer
const renderer = new THREE.WebGLRenderer( { antialias: true } );
renderer.setSize( width, height );
renderer.setAnimationLoop( animate );
document.body.appendChild( renderer.domElement );

// Animation loop
function animate( time ) {
	mesh.rotation.x = time / 2000;
	mesh.rotation.y = time / 1000;
	renderer.render( scene, camera );
}
```

If everything goes well, you should see [this](https://jsfiddle.net/v98k6oze/).

#### Import via modules

```javascript
import * as THREE from 'three';
import { GLTFLoader } from 'three/addons/loaders/GLTFLoader.js';
```

#### Import from CDN

```javascript
<script type="module">
  import * as THREE from 'three';
  import { GLTFLoader } from 'three/addons/loaders/GLTFLoader.js';
</script>
```

### 🌐 Browser Support

Three.js supports these browsers:

- Chrome (desktop & mobile)
- Firefox (desktop & mobile)
- Safari (desktop & mobile)
- Edge (desktop)
- Opera (desktop)

Internet Explorer is not supported.

### 🛠️ Development

#### Prerequisites

- Node.js 12+
- Git

#### Cloning the Repository

```bash
# Clone with full history (2GB+ download)
git clone https://github.com/mrdoob/three.js.git

# OR clone with limited history (faster)
git clone --depth=1 https://github.com/mrdoob/three.js.git
```

#### Setup & Build

```bash
# Install dependencies
npm install

# Start development server
npm start

# Build library
npm run build

# Run tests
npm test

# Run linting
npm run lint

# Fix linting issues
npm run lint-fix
```

### 🤝 Contributing

We love contributions! Please see our [Contributing Guide](.github/CONTRIBUTING.md) for details.

**Before contributing:**
- Check existing issues and PRs
- Fork the repository
- Create a feature branch from `dev`
- Make your changes
- Submit a pull request to the `dev` branch

### 📝 License

[MIT License](LICENSE)

### 🙏 Acknowledgments

Special thanks to all [contributors](https://github.com/mrdoob/three.js/graphs/contributors) who have helped make three.js what it is today!

### 📈 Release History

See [Releases](https://github.com/mrdoob/three.js/releases) for the complete changelog.

---

[npm]: https://img.shields.io/npm/v/three
[npm-url]: https://www.npmjs.com/package/three
[build-size]: https://badgen.net/bundlephobia/minzip/three
[build-size-url]: https://bundlephobia.com/result?p=three
[npm-downloads]: https://img.shields.io/npm/dw/three
[npmtrends-url]: https://www.npmtrends.com/three
[discord]: https://img.shields.io/discord/685241246557667386
[discord-url]: https://discord.gg/56GBJwAnUS
[deepwiki]: https://deepwiki.com/badge.svg
[deepwiki-url]: https://deepwiki.com/mrdoob/three.js

