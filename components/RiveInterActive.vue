<script setup lang="ts">
import { ref, onMounted } from 'vue';
import { Rive } from '@rive-app/canvas';

type Props = {
  src: string,
}

const props = defineProps<Props>();

const canvas = ref<HTMLCanvasElement | null>(null);

onMounted(() => {
  if (canvas.value !== null) {
    new Rive({
      canvas: canvas.value,
      src: props.src,
      autoplay: true,
      stateMachines: "state",
    });
  }
});

</script>

<template>
  <div>
    <canvas ref="canvas" width="400" height="400"></canvas>
  </div>
</template>

<style>
canvas {
  margin: 0 auto;
}
</style>
