# GSAP Motion Path Marquee Slider

A responsive marquee slider built with **GSAP MotionPathPlugin**, where slide items move infinitely along a custom **SVG curved path**.

This creates a dynamic “motion marquee” effect where items follow a smooth curve path while maintaining equal spacing and responsive scaling across screen sizes.

---

## Features

* Infinite marquee animation
* Items move along a custom SVG path
* Responsive scaling for desktop, tablet, and mobile
* Responsive item width adjustment
* Smooth linear animation using GSAP MotionPathPlugin
* Auto-rotating items along the path
* Re-initializes on window resize

---

## Technologies Used

* HTML
* CSS
* JavaScript
* GSAP
* GSAP MotionPathPlugin
* SVG Path Animation

---

## How It Works

Each marquee item animates along the same SVG path using GSAP:

```javascript
motionPath: {
  path: path,
  align: path,
  alignOrigin: [0.5, 0.5],
  start: i * spacing,
  end: i * spacing + 1,
  autoRotate: true
}
```

### Explanation:

* `path`: The SVG path items follow
* `align`: Aligns each item to the SVG path
* `start`: Starting position for each item
* `end`: End position after completing one loop
* `autoRotate`: Rotates items based on path direction

This allows each item to move continuously while keeping equal spacing.

---

## Responsive Configuration

The slider adjusts:

* **animation duration**
* **item scale**
* **item width**

based on screen size.

Example:

```javascript
if (width < 480) {
  return { spacing: 1 / items.length, duration: 8, scale: 0.4, itemWidth: "100px" };
}
```

This ensures:

* smaller items on mobile
* faster animation on small screens
* better spacing without overlap

---

## Initialization Flow

1. Select all marquee items
2. Select the SVG motion path
3. Apply responsive settings
4. Set width and scale for each item
5. Animate each item along the SVG path
6. Recalculate on window resize

---

## Resize Handling

The slider is rebuilt on resize:

```javascript
window.addEventListener("resize", () => {
  clearTimeout(resizeTimeout);

  resizeTimeout = setTimeout(() => {
    initSlider();
  }, 200);
});
```

This keeps spacing and scaling accurate on viewport changes.

---

## Use Cases

This motion marquee is ideal for:

* service highlights
* product tags
* feature labels
* brand badges
* dynamic hero sections
* interactive landing pages

---

## Benefits

* visually engaging
* lightweight
* highly customizable
* responsive
* smooth animation performance
* easy to integrate into landing pages

---

## Future Improvements

Possible enhancements:

* pause on hover
* drag interaction
* dynamic speed controls
* reverse direction support
* multiple motion paths
* scroll-triggered activation

---

## Author

Built using **GSAP MotionPathPlugin** for smooth SVG path-based marquee animation.
