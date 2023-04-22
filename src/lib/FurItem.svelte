<script lang="ts">
  import SIZE from "../constants/size";

  export let column: number;
  export let row: number;

  let div: HTMLDivElement;
</script>

<div
  bind:this="{div}"
  style="{`width: ${SIZE}rem; height: ${SIZE}px; background-color: rgb(${Math.round(
    (column / (window.innerWidth / SIZE)) * 255
  )}, ${Math.round((row / (window.innerHeight / SIZE)) * 255)}, 0)`}"
></div>
