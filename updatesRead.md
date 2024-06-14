Change the `<a-cube>` element to `<a-box>` to mirror the tutorial, but also to render the cube on the screen.

Another fix is the animation code, because it does not work.
After reading the [A-FRAME](https://aframe.io/docs/1.6.0/components/animation.html) docs, for animation, the following changes need to be made on [this](https://github.com/end3r/MDN-Games-3D/blob/gh-pages/A-Frame/shapes.html) file.


```HTML
<!-- 1 -->
<a-cube color="#0095DD" rotation="20 40 0" position="0 1 0">
      <a-animation 
      attribute="rotation"
      from="20 0 0" to="20 360 0"
      direction="alternate"
      dur="4000"
      repeat="indefinite"
      easing="ease">
    </a-animation>
</a-cube
<!-- replace code above with the following -->
<a-box color="#0095DD" position="0 1 0" rotation="20 40 0" animation="property: rotation;from:20 0 0 to: 20 360 0;dir: alternate; loop: true; dur: 4000; easing: easeInOutQuad;"></a-box>

<!-- 2 -->
  <a-entity 
  geometry="
  primitive: torus;
  radius: 1;
  radiusTubular: 0.1;
  segmentsTubular: 12;" 
  material="color: #EAEFF2;
  roughness: 0.1;
  metalness: 0.5;"
  rotation="10 0 0"
  position="-3 1 0">
    <a-animation attribute="scale" to="1 0.5 1" direction="alternate" dur="2000" repeat="indefinite" easing="linear"></a-animation>
    </a-entity>

    <!-- replace code above with the following -->
    <a-entity
            geometry="
            primitive: torus;
            radius: 1;
            radiusTubular: 0.1;
            segmentsTubular: 12;"
            material="
            color: #EAEFF2;
            roughness: 0.1;
            metalness: 0.5;"
            rotation="10 0 0"
            position="-3 1 0"
            animation="property: scale; to: 1 0.5 1; direction: alternate; dur: 2000; repeat: indefinite; easing: linear;">
        
      </a-entity>

```

We also need to update the docs.
