<script lang="ts">
  import { spring } from "svelte/motion";

  let coords = spring(
    { x: 0, y: 0 },
    {
      stiffness: 0.25,
      damping: 0.7,
    },
  );
</script>

<div
  on:mousemove={(e) => {
    coords.set({ x: e.clientX, y: e.clientY });
  }}
>
  <p style="left: {$coords.x}px; top: {$coords.y}px">Hello World!</p>
</div>

<style>
  div {
    width: 100vw;
    height: 100vh;
    position: relative;
  }

  p {
    border: 1px solid black;
    padding: 10px;
    border-radius: 10px;
    position: absolute;
    transform: translate(-50%, -100%);
  }
</style>
