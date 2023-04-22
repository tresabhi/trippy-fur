<script lang="ts">
  import SIZE from "../constants/size";
  import FurRow from "./FurRow.svelte";
</script>

<div id="fur-row">
  {#each { length: window.innerHeight / SIZE } as item, index}
    <FurRow column="{index}" />
  {/each}
</div>

<style>
  #fur-row {
    display: flex;
    flex-direction: column;
  }
</style>
