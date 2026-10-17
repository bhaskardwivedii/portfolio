<div align="center">

# Bhaskar Dwivedi — Portfolio

**AI Product Engineer · Building intelligent products, from data to deployment.**

An interactive portfolio set inside a real-time 3D solar system. Each planet is a section of the site, and every project plays a live preview.

[**Live site →**](https://bhaskar-dwivedi.vercel.app)

![Three.js](https://img.shields.io/badge/Three.js-r158-000000?logo=threedotjs&logoColor=white)
![GSAP](https://img.shields.io/badge/GSAP-ScrollTrigger-88CE02?logo=greensock&logoColor=black)
![WebGL](https://img.shields.io/badge/WebGL-GLSL_shaders-990000?logo=webgl&logoColor=white)
![Vercel](https://img.shields.io/badge/Hosted_on-Vercel-000000?logo=vercel&logoColor=white)

</div>

---

## Overview

The portfolio is a single-page site built around a procedurally rendered solar system. Scrolling flies the camera from planet to planet, and each planet holds one part of the story. Clicking any planet zooms in and opens a preview of that section. Moons orbiting the planets represent the groups inside a section, such as individual projects or skill areas.

Everything in the scene is generated in GLSL at runtime. There are no 3D models or texture files.

## The system

| Planet | Section | What it holds |
|---|---|---|
| **Sol** | Home | Introduction, resume, links |
| **Terra** | About | Background, education, key numbers |
| **Nova** | Projects | Ringed giant with **5 moons**, one per project. Clicking a moon opens that project |
| **Atlas** | Skills | Banded giant with **6 moons**, one per skill group |
| **Aurum** | Achievements | Hackathon results, AWS certifications, LeetCode |
| **Glacia** | Contact | Email, LinkedIn, GitHub, Instagram |

## Features

- **Procedural HD planets.** Each planet has its own fragment shader built on 3D simplex noise and fractal Brownian motion.
  - Terra has continents, oceans with specular glint, moving clouds, polar ice and city lights on the night side.
  - The gas giants have turbulent bands and a storm system.
  - Aurum has gold veins and Glacia has ridged ice.
  - All planets have atmospheric scattering at the rim.
- **Animated sun.** It has surface granulation, limb darkening and a corona with animated rays.
- **Ring shadows.** Planetary rings catch the planet's real shadow, computed per pixel.
- **Starfield and nebula.** The background is baked once into a cubemap so it costs almost nothing per frame. An asteroid belt orbits between the outer planets.
- **Post-processing.** HDR rendering with bloom from a mipmap chain, ACES tone mapping and a vignette. Fast scrolling adds radial warp streaks and chromatic aberration.
- **Planet focus.** Click a planet or its label and the camera flies in. A glass panel previews that section, with shortcuts into the full content.
- **Warp rail.** A translucent navigator on the screen edge shows one stop per planet and a draggable handle to travel through the page. While scrolling, a readout shows speed in light-years per second, a warp factor and the next destination. Hovering a stop previews that section.
- **Live project previews.** Each project card plays a preview inside a browser frame:
  - **CardioSense** and **TrustChain** show real screen recordings of the running applications, with galleries of real screenshots in the detail view.
  - **Insurance DApp**, **Smart Task Management System** and **Duplicate Question Detection** run interactive prototypes in the page. The insurance prototype follows the rules of the project's Solidity contract. The duplicate-question demo computes TF-IDF cosine similarity live for any two questions typed in.
- **Motion.**
  - Smooth inertial scrolling and a pinned horizontal project gallery.
  - Character-level text reveals, scramble effects and scroll-linked word highlighting.
  - Magnetic buttons and a custom cursor.
- **GitHub data.** Project detail views fetch languages, last update and stars from the GitHub API, and hide that block if the request fails.
- **Adaptive quality.** The render resolution lowers itself on devices that can't hold a smooth frame rate, and phones get lighter geometry and fewer particles.
- **Accessible.**
  - Every interactive element is a real link or button with a visible focus state.
  - Keyboard support includes Esc to close panels and arrow keys on the rail.
  - `prefers-reduced-motion` turns off non-essential animation.
  - The layout is fully responsive down to phone width.

## Featured projects

| Project | Stack | Links |
|---|---|---|
| **CardioSense** — Hybrid deep learning model for cardiovascular disease prediction | Python, Autoencoder, DNN, Particle Swarm Optimization, Scikit-learn | [Live app](https://cardiosense-ovtw.onrender.com/) · [Code](https://github.com/bhaskardwivedii/cardiosense) |
| **TrustChain** — Certificate verification DApp | Ethereum, Solidity, ethers.js, MetaMask, Ganache | [Code](https://github.com/bhaskardwivedii/certificate_verification_dapp) |
| **Insurance DApp** — Decentralized insurance claims | Solidity, Ethereum, Truffle | [Code](https://github.com/bhaskardwivedii/insurance-dapp) |
| **Smart Task Management System** — Real-time task platform | React.js, Node.js, Express.js, MongoDB, Socket.io, JWT | — |
| **Duplicate Question Detection** — NLP on 400,000+ Quora question pairs | Python, TF-IDF, Scikit-learn, XGBoost, Pandas, NumPy | — |

## Tech stack

| Area | Tools |
|---|---|
| 3D and rendering | Three.js (r158), custom GLSL shaders, WebGL render targets |
| Motion | GSAP 3 + ScrollTrigger, Lenis smooth scroll |
| Interface | Semantic HTML, modern CSS (grid, `backdrop-filter`, custom properties), vanilla JavaScript |
| Typography | Unbounded, Instrument Serif, Manrope, JetBrains Mono (Google Fonts) |
| Media | H.264 screen recordings and optimised JPEG screenshots |
| Hosting | Vercel (static, with long-lived caching for assets) |

The site needs no build step. Libraries load from public CDNs.

## Project structure

```
.
├── index.html        # Page, styles, scene, shaders and interactions
├── resume.pdf        # Resume linked across the site
├── vercel.json       # Clean URLs and caching headers
└── assets/
    ├── cardio.mp4            # CardioSense screen recording
    ├── vericert.mp4          # TrustChain screen recording
    ├── *_poster.jpg          # Video posters
    ├── cs_*.jpg              # CardioSense screenshots
    └── vc_*.jpg              # TrustChain screenshots
```

## Running locally

Any static file server works. For example:

```bash
python3 -m http.server 8080
```

Then open `http://localhost:8080`. Opening `index.html` directly from disk also works, but the GitHub API requests and video loading behave best over HTTP.

## Browser support

The site works in current versions of Chrome, Edge, Firefox and Safari on desktop and mobile. It needs WebGL; WebGL2 gets HDR bloom. Without WebGL, all content stays readable and navigable.

## Contact

- **Email:** bhaskardwivedi.24112004@gmail.com
- **LinkedIn:** [linkedin.com/in/bhaskardwivedii](https://www.linkedin.com/in/bhaskardwivedii/)
- **GitHub:** [github.com/bhaskardwivedii](https://github.com/bhaskardwivedii)
- **Instagram:** [@bhaskar.dwivedii](https://www.instagram.com/bhaskar.dwivedii/)

---

<div align="center">

© 2026 Bhaskar Dwivedi. All rights reserved.

</div>
