<html>
  <head>
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <script src="../../dist-dev/mindar.image.js"></script>
    <script src="https://aframe.io/releases/1.2.0/aframe.min.js"></script>
    <script src="https://cdn.jsdelivr.net/gh/donmccurdy/aframe-extras@v6.1.1/dist/aframe-extras.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/stats.js/16/Stats.min.js"></script>
    <script src="../../dist-dev/mindar.image-aframe.js"></script>
   
    <style>
      body {
        margin: 0;
      }
      .example-container {
        overflow: hidden;
        position: absolute;
        width: 100%;
        height: 100%;
      }
    </style>
  </head>

  <body>
    <div class="example-container">
      <a-scene mindar.image="imageTargetSrc: ./assets/targets.mind; showStats: true;" embedded color-space="sRGB" renderer="colorManagement: true, physicallyCorrectLights" vr-mode-ui="enabled: false" device-orientation-permission-ui="enabled: false">
        <a-assets>
          <img id="card" src="./assets/wireframe.png" />
          <a-asset-item id="avatarModel" src="./assets/Flate_Interior.gltf"></a-asset-item>
        </a-assets>

        <a-camera position="0 0 0" look-controls="enabled: false"></a-camera>

        <a-entity mindar.image-target="targetIndex: 0">
          <a-plane src="#card" position="0 0 0" height="0.552" width="1" rotation="0 0 0"></a-plane>

          <a-gltf-model rotation="0 0 0 " position="0 0 0.1" scale="0.005 0.005 0.005" src="#avatarModel"
            animation="property: position; to: 0 0.1 0.1; dur: 1000; easing: easeInOutQuad; loop: true; dir: alternate"
          >
        </a-entity>
      </a-scene>
    </div>
  </body>
</html>
