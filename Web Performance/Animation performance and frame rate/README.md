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

- Compared with animating elements using JavaScript, CSS animations can be easier to create. They can also give better performance, as they give the browser more control over when to render frames, and to drop frames if necessary.

- However, the performance cost of modifying a CSS property can vary from one property to another. It's commonly accepted that 60 frames per second is the rate at which animations will appear smooth. For a rate of 60 frames per second, the browser has `16.7 milliseconds` to execute scripts, recalculate styles and layout if needed, and repaint the area being updated. Slow scripts and animating expensive CSS properties can result in jank as the browser struggles to hit a smooth frame rate.

- The rendering waterfall: The process a browser uses to paint changes to a page when an element is animating CSS properties can be described as a waterfall consisting of the following steps:
  1. Recalculate Style: when a property for an element changes, the browser must recalculate computed styles.
  2. Layout: next, the browser uses the computed styles to figure out the position and geometry for the elements. This operation is labeled "layout" but is also sometimes called "reflow".
  3. Paint: finally, the browser needs to repaint the elements to the screen. One last step is not shown in this sequence: the page may be split into layers, which are painted independently and then combined in a process called "Composition".

  This sequence needs to fit into a single frame, since the screen isn't updated until it is complete.

- Both CSS transitions and animations can be used to write animation. They each have their own user scenarios.

- CSS transitions provide an easy way to make animations occur between the current style and an end CSS state, e.g., a resting button state and a hover state. Even if an element is in the middle of a transition, the new transition starts from the current style immediately instead of jumping to the end CSS state.

- CSS animations, on the other hand, allow developers to make animations between a set of starting property values and a final set rather than between two states. CSS animations consist of two components: a style describing the CSS animation, and a set of key frames that indicate the start and end states of the animation's style, as well as possible intermediate points.

- JS Animation | requestAnimationFrame: API provides an efficient way to make animations in JavaScript. The callback function of the method is called by the browser before the next repaint on each frame. Compared to setTimeout()/setInterval(), which need a specific delay parameter, requestAnimationFrame() is much more efficient. Developers can create an animation by changing an element's style each time the loop is called (or updating the Canvas draw, or whatever.) 

