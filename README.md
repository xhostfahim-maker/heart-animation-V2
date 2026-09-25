# Heart Animation

A mesmerizing, lightweight HTML5 Canvas animation featuring a mathematically modeled pulsating heart, glowing synchronized initials, and drifting romantic particles. Built entirely with pure **Vanilla JavaScript, HTML5 Canvas, and CSS3**—zero external runtime frameworks or heavy dependencies required.

---

## ✨ Features

- **🫀 Mathematical Heart Engine**: Real-time parametric cardioid curve rendered with high-performance particle pool physics.
- **💫 Glowing Center Initials**: Customizable monogram (**H ♡ A**) glowing in warm champagne-gold and ruby-rose, pulsing in complete sync with the heartbeat.
- **✏️ In-Browser Live Editing**: Click directly on the center initials in any browser to type custom names or messages—automatically persisted to `localStorage`.
- **🌸 Drifting Heart Particles**: Ambient background particles drifting smoothly across the screen in dynamic pastel palettes.
- **📱 Fully Responsive**: Automatically adjusts to any screen size (mobile, tablet, ultra-wide desktop) with window resize recalculations.
- **⚡ Lightweight & Fast**: 60 FPS animation loop with `requestAnimationFrame` and particle pooling for zero garbage-collection stutter.

---

## 🧮 Mathematical Formulation

The core heart shape is computed using the classical parametric heart curve:

$$\begin{aligned}
x(t) &= 160 \sin^3(t) \\
y(t) &= 130 \cos(t) - 50 \cos(2t) - 20 \cos(3t) - 10 \cos(4t) + 25
\end{aligned}$$

Where:
- $t \in [-\pi, \pi]$ traverses the complete perimeter of the heart.
- Velocity vectors and cubic easing functions (`ease(t) = --t * t * t + 1`) control particle trajectory, scale, and dispersion outward from the contour.

---

## 🚀 Quick Start

No installation, build tools, or server setup required.

1. **Clone or Download** this repository:
   ```bash
   git clone https://github.com/your-username/heart-animation.git
   ```
2. **Open the Animation**:
   - Simply double-click [`index.html`](index.html) to open it in your favorite web browser (Chrome, Edge, Safari, Firefox).
   - Alternatively, serve it via any static server:
     ```bash
     # Using Python
     python -m http.server 8000

     # Using Node.js
     npx serve .
     ```

---

## 🛠️ Customization Guide

### 1. Changing the Center Initials
You have two easy ways to customize the initials:

- **Directly on Screen**: Open the webpage in your browser, click on the center text (`H ♡ A`), and type your own initials or names. Press **Enter** to save.
- **In the Code**: Open [`index.html`](index.html) and edit line `219`:
  ```html
  <div id="name" contenteditable="true" spellcheck="false" title="Click to edit initials">
    H <span class="heart-icon">♡</span> A
  </div>
  ```

### 2. Changing the Floating Particle Text
To change the floating message (default: `"💗 I Love You 💗"`), locate the `Heart.prototype.draw` method in [`index.html`](index.html):
```javascript
ctx.fillText(
  "💗 I Love You 💗", // Replace with your custom message or name
  this.x - this.width * 0.5,
  this.y - this.height * 0.5,
  this.width,
  this.height
);
```

### 3. Adjusting Particle Speed and Density
Modify the `settings` object in [`index.html`](index.html) to fine-tune the particle heart:
```javascript
var settings = {
  particles: {
    length: 500,    // Maximum number of active particles
    duration: 2,    // Lifetime of each particle in seconds
    velocity: 100,  // Speed in pixels/second
    effect: -0.75,  // Acceleration decay effect
    size: 30,       // Particle size in pixels
  },
};
```

---

## 🌐 Deploying to GitHub Pages (Share Online)

To share this animation with someone special via a live URL:

1. Push this project to a GitHub repository.
2. Go to **Settings** > **Pages** in your repository.
3. Under **Branch**, select `main` (or `master`) and folder `/ (root)`.
4. Click **Save**. Within moments, your site will be live at:
   ```text
   https://<your-username>.github.io/<repo-name>/
   ```

---

## 📁 Project Structure

```text
├── index.html        # Main HTML5 entry point containing Canvas engine and styles
└── README.md         # Documentation and customization guide
```

---

## 💻 Tech Stack

- **HTML5 Canvas API** (`2D Context`)
- **CSS3 Animations & Keyframes** (Synchronized heart-beat pulsing & layered text-shadow glows)
- **Vanilla JavaScript** (Particle pooling, parametric math, window resize handling, `localStorage`)
- **Google Fonts** (*Dancing Script*, *Playfair Display*)

---

## 📄 License

This project is open-source and free to use for personal romantic surprises, gifts, and creative web experiments!
