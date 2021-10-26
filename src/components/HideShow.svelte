<script type="ts">
	export let startShow: boolean = false;
	let show = startShow;
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
