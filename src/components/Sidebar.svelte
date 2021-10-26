<script lang="ts">
	export let darkmode: boolean;

	let sy: number = 0;
	let sMover: string = '0px';
	//20 from the top and bottom margins

	export let items: { name: string; link: string; height: number }[] = [];

	let internalItems: typeof items;

	$: {
		let m = 0;
		internalItems = items.map((a) => {
			a.height += m;
			m = a.height;
			return a;
		});
	}

	$: {
		if (items.length === 0) sMover = '-100px';
		let c = 0;
		for (let item of items) {
			if (item.height > sy) {
				break;
			}
			c++;
		}
		if (items.length === c) c = -10;

		sMover = `calc(24px + ${c * 2.1}em)`;
	}
</script>

<svelte:window bind:scrollY={sy} />

<div class:darkmode class="sidebar">
	<div class="mover" style={`top: ${sMover};`} />
	<div class="links">
		{#each internalItems as item, i}
			<div class="link">
				<a href={item.link}>
					{item.name}
				</a>
			</div>
		{/each}
	</div>
</div>

<style>
	.sidebar {
		position: sticky;
		top: 0;
		left: 0;
		width: 25ch;
		color: black;
		place-self: start;
		padding-top: 20px;
	}
	.darkmode.sidebar {
		color: white;
	}
	.sidebar .links {
		padding: 10px;
	}
	.sidebar .link {
		margin-bottom: 1em;
	}
	.sidebar a {
		font-weight: 700;
		text-decoration: none;
		font-size: 1em;
		color: black;
	}
	.darkmode.sidebar a {
		color: white;
	}
	.links {
		margin: 20px 0px 0px calc(5px + 1em);
		position: relative;
		top: calc(-1em - 10px);
	}
	.mover {
		height: 0.7em;
		width: 0.7em;
		position: absolute;
		border-radius: 50%;
		left: 10px;
		background-color: black;
		transition: top 0.7s;
	}
	.darkmode .mover {
		background-color: white;
	}
	@media only screen and (max-width: 1100px) {
		.sidebar {
			display: none;
		}
	}
</style>
