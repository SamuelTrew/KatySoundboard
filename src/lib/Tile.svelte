<script lang="ts">
  type Props = {
    icon: string
    music: string
  }

	let {icon, music}: Props = $props();
  let highlight = $state(false)

  const play = () => {
    const audio = new Audio(`/${music}`)
    audio.onended = () => {
      highlight = false
    }
    audio.onplay = () => {
      highlight = true
    }
    audio.play()
  }
</script>

<button onclick={play} class={`tile ${highlight ? "highlighted": ""}`}>
  <img loading="lazy" src={`/${icon}`} alt={icon} width={80} height={80} />
</button>

<style lang="scss">
  .tile {
    padding: 0;
    height: 100%;
    width: 100%;
    border: 1px solid hotpink;
    &:hover {
      background-color: hotpink;
    }

    img {
      border-radius: 0.5rem;
    }
  }

  .highlighted {
    background-color: red;
    border: 1px solid red;

    &:hover {
      background-color: darkred;
    }
  }
</style>