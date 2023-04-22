<script lang="ts">
  import FurRow from "./FurRow.svelte";
</script>

<div id="fur-row">
  {#each { length: window.innerHeight / 16 } as item, index}
    <FurRow column="{index}" />
  {/each}
</div>

<style>
  #fur-row {
    display: flex;
    flex-direction: column;
  }
</style>
