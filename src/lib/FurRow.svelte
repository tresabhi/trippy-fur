<script lang="ts">
  import SIZE from "../constants/size";
  import FurItem from "./FurItem.svelte";

  export let column: number;
</script>

<div id="fur-row">
  {#each { length: window.innerWidth / SIZE } as item, index}
    <FurItem column="{column}" row="{index}" />
  {/each}
</div>

<style>
  #fur-row {
    display: flex;
  }
</style>
