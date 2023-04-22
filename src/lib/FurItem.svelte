<script lang="ts">
  import { onMount } from "svelte";

  export let column: number;
  export let row: number;

  let div: HTMLDivElement;
  const RANGE = 150;

  onMount(() => {
    // div.style.backgroundColor = `rgb(${
    //   Math.round(Math.random() * RANGE) + 255 - RANGE
    // }, ${Math.round(Math.random() * RANGE) + 255 - RANGE}, ${
    //   Math.round(Math.random() * RANGE) + 255 - RANGE
    // })`;
  });
</script>

<div
  bind:this="{div}"
  style="{`width: 1rem; height: 1rem; background-color: rgb(${Math.round(
    (column / (window.innerWidth / 16)) * 255
  )}, ${Math.round((row / (window.innerHeight / 16)) * 255)}, 0)`}"
></div>
