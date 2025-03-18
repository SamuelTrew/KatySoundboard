<script lang="ts">
  import Tile from './lib/Tile.svelte'
  const tiles = [
    {icon: "scissors.svg", music: "test.mp3"},
    {icon: "hand.svg", music: "test.mp3"},
    {icon: "wicked.jpg", music: "test.mp3"},
    {icon: "wheatus.png", music: "test.mp3"},
    {icon: "boy.svg", music: "test.mp3"},
    {icon: "where.svg", music: "test.mp3"},
  ]
</script>

<main>
  <div class="grid">
    {#each tiles as {icon, music}}
      <Tile icon={icon} music={music} />
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
