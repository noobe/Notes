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

- Users expect all interface interactions to be smooth and all user interfaces to be responsive. Animation can help make a site feel faster and responsive, but animations can also make a site feel slower and janky if not done correctly. Responsive user interfaces have a frame rate of 60 frames per second (fps). While it is not always possible to maintain 60fps, it is important to maintain a high and steady frame rate for all animations.

- With CSS animations you specify a number of keyframes, each of which uses CSS to define the appearance of the element at a particular stage of the animation. The browser creates the animation as a transition from each keyframe to the next.

- With CSS animations you specify a number of keyframes, each of which uses CSS to define the appearance of the element at a particular stage of the animation. The browser creates the animation as a transition from each keyframe to the next.