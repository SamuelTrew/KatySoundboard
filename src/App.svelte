<script lang="ts">
  import Tile from './lib/Tile.svelte'
</script>

<main>
  <div class="grid">
    {#each { length: 9 }, rank}
      <Tile />
    {/each}
  </div>
</main>

<style lang="scss">
  .grid {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    grid-template-rows: 1fr 1fr 1fr;
    column-gap: 1rem;
    row-gap: 1rem;
  }
</style>
