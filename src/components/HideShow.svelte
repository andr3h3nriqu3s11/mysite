<script>
	let show = false;
</script>

<button
	class="readmore"
	on:click={() => {
		show = !show;
	}}
>
	{#if !show}
		Read More
	{:else}
		Close
	{/if}
</button>

{#if show}
	<slot />
{/if}

<style>
	.readmore {
		font-size: 1rem;
		color: grey;
		cursor: pointer;
		background: none;
		border: none;
		outline: none;
	}
</style>
