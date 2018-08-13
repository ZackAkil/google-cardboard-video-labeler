# google-cardboard-video-labeler
System of labelling data for "object tracking" machine learning.  

## useful resources

 - A-frame, as the VR framework https://aframe.io/
 
 - raycaster, allows us to pin point where on an object the user is looking https://aframe.io/docs/0.8.0/components/raycaster.html#events_raycaster_intersected

- lower down rayaster library
https://threejs.org/docs/#api/core/Raycaster

- figure out how to get contious intersection data by clearing `intersectedEls` from raycaster on `raycaster-intersected` event:

```js
    AFRAME.registerComponent('collider-check', {
      dependencies: ['raycaster'],

      init: function () {
        this.el.addEventListener('raycaster-intersected', function (event) {

          event.detail.el.components.raycaster.intersectedEls = [];

          console.log(event.detail.intersection.point);

        });
      }
    });
```
source info (raycaster code)
https://github.com/aframevr/aframe/blob/8809e7fd5eccd4c4ce76892f4a5673b911dfd60f/src/components/raycaster.js

- video controls https://github.com/oscarmarinmiro/aframe-video-controls
