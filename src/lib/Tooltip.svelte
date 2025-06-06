<script lang="ts">
  import type { Snippet } from "svelte";

   type Props = {
      title: string
      children: Snippet
   }

	let {title, children}: Props = $props();
	let isHovered = $state(false);
	let x = $state(0);
	let y = $state(0);

	function mouseOver(event: MouseEvent) {
		isHovered = true;
		x = event.pageX + 5;
		y = event.pageY + 5;
	}
	function mouseMove(event: MouseEvent) {
		x = event.pageX + 5;
		y = event.pageY + 5;
	}
	function mouseLeave() {
		isHovered = false;
	}
</script>

<div
	onmouseenter={mouseOver}
   onmouseleave={mouseLeave}
	onmousemove={mouseMove}
   role="tooltip">
	{@render children?.()}
</div>

{#if isHovered}
	<div style="top: {y}px; left: {x}px;" class="tooltip">{title}</div>
{/if}

<style lang="scss">
	.tooltip {
		border: 1px solid #333;
		box-shadow: 1px 1px 1px #333;
		background: black;
		border-radius: 4px;
		padding: 4px;
		position: absolute;
	}
</style>