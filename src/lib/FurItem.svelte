<script lang="ts">
  import { onDestroy } from "svelte";
  import { FRAME_RATE, SIZE } from "../constants/rendering";
  import { noise } from "../utilities/noise";

  export let column: number;
  export let row: number;

  let div: HTMLDivElement;
  let prong: HTMLDivElement;

  const interval = setInterval(() => {
    const time = new Date().getTime() / 400;
    const value = noise(column + time / 10, row / 10);

    prong.style.transform = `rotate(${
      value * 45 + Math.sin(time / 10) * 45
    }deg)`;
    prong.style.opacity = `${value / 2 + 0.5}`;
    prong.style.width = `${(value * SIZE) / 2 + SIZE / 2}px`;
    prong.style.backgroundColor = `rgb(255, 128, ${Math.round(value * 255)})`;
  }, 1000 / FRAME_RATE);

  onDestroy(() => {
    clearInterval(interval);
  });
</script>

<div
  bind:this="{div}"
  style="{`width: ${SIZE}rem; height: ${SIZE}px;`}"
  id="container"
>
  <div
    bind:this="{prong}"
    id="prong"
    style="{`border-radius: ${SIZE / 32}px; height: ${SIZE / 16}px;`}"
  ></div>
</div>

<style>
  #container {
    position: relative;
  }

  #prong {
    background-color: white;
    position: absolute;
    transform-origin: left center;
  }
</style>
