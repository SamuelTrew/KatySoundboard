<script lang="ts">
   import Tooltip from "./Tooltip.svelte";

   type Props = {
      icon: string
      music: string
      authors: string[]
   }

	let {icon, music, authors}: Props = $props();
   let highlight = $state(false)

   const audio = new Audio(`/music/${music}`)
   audio.volume = 0.5
   audio.onended = () => {
      highlight = false
   }
   audio.onplay = () => {
      highlight = true
   }

   const play = () => {
      if (!audio.paused) {
         audio.pause()
      } else {
         audio.play()
      }
   }
</script>

<button onclick={play} class={`tile ${highlight ? "highlighted": ""}`}>
   <Tooltip title={authors.join(", ")}>
      <img loading="lazy" src={`/icons/${icon}`} alt={icon} width={80} height={80} />
   </Tooltip>
</button>

<style lang="scss">
   .tile {
      padding: 0;
      height: 80px;
      width: 80px;
      border: 1px solid pink;
      &:hover {
         background-color: pink;
      }

      img {
         border-radius: 0.5rem;
      }
   }

   .highlighted {
      background-color: lightpink;
      border: 1px solid lightpink;

      &:hover {
         background-color: hotpink;
      }
   }
</style>