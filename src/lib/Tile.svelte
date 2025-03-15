<script lang="ts">
  let count: number = $state(0)
  const increment = () => {
    count += 1
  }
</script>

<button onclick={increment} class="tile">
  count is {count}
</button>

<style lang="scss">
  .tile {
    height: 100%;
    width: 100%;
    background-color: lightblue;
    &:hover {
      background-color: bisque;
    }
  }
</style>