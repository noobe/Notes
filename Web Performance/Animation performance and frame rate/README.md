# Animation Performance and Framerate
- Animation on the web can be done using:
  1. CSS
  2. JS + CSS
  3. SVG
  4. Canvas and WebGL
  5. Videos
  6. Animated GIFs/PNGs and other image types

- The performance cost of CSS animation varies with the type and animating expensive CSS properties can result in jank* as the browser struggles to hit a smooth frame rate.

*Jank refers to sluggishness in a user interface, usually caused by executing long tasks on the main thread, blocking rendering, or expending too much processor power on background processes.

- For animated media like Video, GIFs - the main concern is the files size.

- Code based animations like CSS, JS, SVG, Canvas etc may have smaller size but might end up taking up more CPU cycles to perform and may cause jank.