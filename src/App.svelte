<script lang="ts">
  import Tile from './lib/Tile.svelte'
  import Header from './lib/Header.svelte';

  const tiles = [
    {icon: "espresso.svg", music: "espresso.mp3", authors: ["Sam", "Newman", "WeiWei", "Lav", "Hao"]},
    {icon: "coke.png", music: "coke.m4a", authors: ["Yiming"]},
    {icon: "boy.svg", music: "boy.mp3", authors: ["Newman", "Sam", "WeiWei", "Hao"]},
    {icon: "snowflake.png", music: "chasing-cars-scottish.mp3", authors: ["Will"]},
    {icon: "cat.png", music: "meow.mp3", authors: ["WeiWei", "Hao", "Sam", "Newman"]},
    {icon: "wicked.jpg", music: "wicked.mp3", authors: ["Lav"]},
    {icon: "egypt.png", music: "denial.mp3", authors: ["Erin", "Nick"]},
    {icon: "boq.png", music: "boq.mp3", authors: ["Zailah"]},
    {icon: "dirt.png", music: "dirtbag.mp3", authors: ["Newman", "Hao"]},
    {icon: "where.svg", music: "where-are-you.mp3", authors: ["Newman", "Hao", "Lav", "Sam"]},
    {icon: "girl.png", music: "girlfriend.m4a", authors: ["Newman"]},
    {icon: "scissors.svg", music: "suffocation.mp3", authors: ["Sam", "Hao", "Newman"]},
  ]
</script>

<main class="main">
  <Header />
  <div class="app-body">
    <div class="grid">
      {#each tiles as tile}
        <Tile {...tile} />
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
