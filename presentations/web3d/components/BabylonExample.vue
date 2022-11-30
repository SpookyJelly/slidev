<script setup lang="ts">
import {
  FreeCamera,
  Engine,
  Vector3,
  CreateGround,
  CreateSphere,
  Scene,
  HemisphericLight,
} from "@babylonjs/core";
import { GridMaterial } from "@babylonjs/materials";
import { onMounted, ref, watchEffect } from "vue";

const canvas = ref<HTMLCanvasElement>();
// const canvas = document.getElementById("renderCanvas") as HTMLCanvasElement;

//build babylon engine
// const engine = new Engine(canvas.value!);

onMounted(() => {
  if (canvas.value) {
    const engine = new Engine(canvas.value);

    const scene = new Scene(engine);

    const camera = new FreeCamera("camera1", new Vector3(0, 5, -10), scene);

    camera.setTarget(Vector3.Zero());
    camera.attachControl(canvas, true);

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
  } else {
    console.log("doom");
  }
  console.info("asdasdasd");
});
</script>

<template>
  <div id="babylon-canvas-wrapper">
    <canvas id="babylon-canvas" ref="canvas"></canvas>
  </div>
</template>

<style scoped>
#babylon-canvas-wrapper {
  max-width: 700px;
}
</style>
