<script lang="ts">
   let display = $state("none")

   const play = () => {
      if (display === "none") {
         display = "block"
      } else {
         display = "none"
      }
   }
</script>

<div class="header">
   <span class="title">Katy Soundboard</span>

   <button onclick={play}>Video?</button>

   <div class="video" style="--display: {display}">
      <iframe
         src="https://drive.google.com/file/d/1MkhrMD4xrLwR0YiIh9eOYzqdQUU7GgF9/preview"
         width="640"
         height="480"
         allow="autoplay"
         title="will video">
      </iframe>
   </div>
</div>

<style lang="scss">
   .header {
      background-color: hotpink;
      display: flex;
      flex-direction: row;
      justify-content: space-between;
      align-items: center;
      padding: 0.25rem 1rem;
   }

   .title {
      font-size: 1.5rem;
   }

   .video {
      position: absolute;
      display: var(--display);
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
   }
</style>