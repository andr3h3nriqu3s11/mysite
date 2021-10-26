<script>
	import '../css/generic.css';

	export let darkmode = false;
	export let link = '';
	export let faviconLink = '';
	export let title = '';
	export let noLogo = false;
</script>

<div class="item-holder text-center" class:darkmode class:noLogo>
	{#if !noLogo}
		<div class="img">
			<img src={faviconLink} alt={`${title} favicon`} />
		</div>
	{/if}
	<div class="title">
		{title}
	</div>
	<div>
		<slot />
	</div>
	<div>
		<a class="no-color-visited" href={link}>Click here to visit!</a>
	</div>
</div>

<style>
	.item-holder {
		display: grid;
		font-size: 1rem;
		grid-template-columns: auto;
		grid-template-rows: 70px 2rem auto 2rem;
		width: 30%;
		border-radius: 10px;
		padding: 1.1rem 3px;
		justify-content: center;
		row-gap: 0.7rem;
		margin-bottom: 30px;
		background-color: #f2f2f2;
		box-shadow: #cccccc 0px 0px 15px;
	}
	.item-holder.noLogo {
		grid-template-rows: 2rem auto 2rem;
	}
	.item-holder.darkmode {
		background-color: #2b2b2b;
		box-shadow: #1e1e1e 0px 0px 15px;
	}
	.img {
		display: grid;
		place-items: center;
	}
	.img img {
		max-height: 70px;
		height: 70px;
		width: auto;
	}
	.title {
		font-size: 1.3rem;
		font-weight: 600;
	}

	@media only screen and (max-width: 700px) {
		.item-holder {
			width: 95%;
		}
	}
</style>
