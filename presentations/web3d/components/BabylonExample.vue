<script setup lang="ts">
import {
  FreeCamera,
  Engine,
  Vector3,
  CreateGround,
  CreateSphere,
  Scene,
  HemisphericLight,
  ArcRotateCamera,
} from "@babylonjs/core";
import { GridMaterial } from "@babylonjs/materials";
import { onMounted, ref } from "vue";

const canvas = ref<HTMLCanvasElement>();

onMounted(() => {
  if (canvas.value) {
    const engine = new Engine(canvas.value);

    const scene = new Scene(engine);

    const camera = new ArcRotateCamera(
      "camera",
      -Math.PI / 2,
      Math.PI / 2.5,
      5,
      new Vector3(0, 2, -3),
      scene
    );
    // camera.setTarget(Vector3.Zero());
    camera.attachControl(canvas, false);

    const light = new HemisphericLight("light1", new Vector3(0, 1, 0), scene);
    light.intensity = 0.7;

    const material = new GridMaterial("grid", scene);
    const sphere = CreateSphere("sphere", { segments: 16, diameter: 2 }, scene);
    sphere.position.y = 2;
    sphere.material = material;

    const ground = CreateGround(
      "ground",
      { width: 6, height: 6, subdivisions: 2 },
      scene
    );
    ground.material = material;

    engine.runRenderLoop(() => {
      scene.render();
    });
  }
});
</script>

<template>
  <div id="babylon-canvas-wrapper">
    <canvas id="babylon-canvas" ref="canvas"></canvas>
  </div>
</template>

<style scoped>
#babylon-canvas-wrapper {
  width: 400px;
  aspect-ratio: 16/8;
}
#babylon-canvas {
  width: 100%;
  height: 100%;
}
</style>
