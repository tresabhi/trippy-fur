<script lang="ts">
  import { SIZE } from "../constants/rendering";
  import FurRows from "./FurRows.svelte";
</script>

<div id="fur-row">
  {#each { length: window.innerHeight / SIZE } as item, index}
    <FurRows column="{index}" />
  {/each}
</div>

<style>
  #fur-row {
    display: flex;
    flex-direction: column;
  }
</style>
