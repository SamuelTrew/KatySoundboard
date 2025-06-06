<script lang="ts">
  import Tile from './lib/Tile.svelte'
  import Header from './lib/Header.svelte';

  const tiles = [
    // {icon: "scissors.svg", music: "test.mp3"},
    // {icon: "hand.svg", music: "test.mp3"},
    // {icon: "wicked.jpg", music: "test.mp3"},
    // {icon: "wheatus.png", music: "test.mp3"},
    // {icon: "boy.svg", music: "test.mp3"},
    // {icon: "where.svg", music: "test.mp3"},
    // {icon: "river.svg", music: "test.mp3"},
    // {icon: "365.svg", music: "test.mp3"},
    {icon: "espresso.svg", music: "espresso.mp3"},
    {icon: "coke.png", music: "coke.m4a"},
    {icon: "snowflake.png", music: "chasing-cars-scottish.mp3"},
    {icon: "cat.png", music: "meow.mp3"},
    {icon: "wicked.jpg", music: "wicked.mp3"},
    {icon: "egypt.png", music: "denial.mp3"},
    {icon: "boq.png", music: "boq.mp3"}
  ]
</script>

<main class="main">
  <Header />
  <div class="app-body">
    <div class="grid">
      {#each tiles as {icon, music}}
        <Tile icon={icon} music={music} />
      {/each}
    </div>
  </div>
</main>

<style lang="scss">
  .main {
    height: 100%;
    width: 100%;
  }

  .app-body {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    height: 100%;
    width: 100%;
  }

  .grid {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    grid-template-rows: 1fr 1fr 1fr;
    column-gap: 1rem;
    row-gap: 1rem;
  }
</style>
