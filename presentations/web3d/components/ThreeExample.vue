<script setup lang="ts">
import * as THREE from "three";
import { ArcballControls } from "three/examples/jsm/controls/ArcballControls";
import { onMounted, ref, onActivated } from "vue";

const webgl = ref<HTMLCanvasElement>();
onMounted(() => {
  const canvas = webgl.value;
  const sizes = {
    width: 360,
    height: 200,
  };

  if (canvas) {
    /* camera */
    const camera = new THREE.PerspectiveCamera(
      70,
      sizes.width / sizes.height,
      1,
      1000
    );
    camera.position.y = 0;
    camera.position.z = 55;

    /* scene */
    const scene = new THREE.Scene();
    scene.background = new THREE.Color("rgb(51,51,75)");

    /** light */

    const pointLight = new THREE.PointLight(0xffffff);
    pointLight.position.set(500, 500, 50);
    scene.add(pointLight);

    /** Object */

    const sphere = new THREE.Mesh(
      new THREE.SphereGeometry(6, 36, 100),
      new THREE.MeshPhongMaterial({ color: 0xe0e0e0 })
    );
    scene.add(sphere);

    /** Plane */

    const plane = new THREE.Mesh(
      new THREE.PlaneGeometry(40, 40),
      new THREE.MeshBasicMaterial({ color: 0xe0e0e0 })
    );

    plane.position.y = -20;
    plane.rotation.x = -Math.PI / 2;

    scene.add(plane);

    /** Renderer */
    const renderer = new THREE.WebGLRenderer({ canvas, antialias: true });

    // ArcballControl은 tick에서 controls.update()할 필요가 없다
    const controls = new ArcballControls(camera, renderer.domElement);

    const tick = () => {
      renderer.render(scene, camera);
      window.requestAnimationFrame(tick); // <-- must be required
    };
    tick();
  }
});
</script>
<template>
  <div id="THREE-canvas-wrapper">
    <canvas id="THREE-canvas" ref="webgl"></canvas>
  </div>
</template>
<style scoped>
#THREE-canvas-wrapper {
  width: 400px;
  aspect-ratio: 16/8;
}
#THREE-canvas {
  width: 100%;
  height: 100%;
}
</style>
