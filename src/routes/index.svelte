<script lang="ts">
	import { onMount } from 'svelte';

	function isDarkModeEnabled() {
		if (typeof window !== 'undefined' && typeof window.matchMedia !== 'undefined') {
			const mediaQueryString = '(prefers-color-scheme: dark)';

			return window.matchMedia(mediaQueryString).matches;
		} else {
			//throw new Error('matchMedia is not supported');
			return false;
		}
	}

	let darkmode = false;

	onMount(() => {
		darkmode = isDarkModeEnabled();
	});
</script>

<main class:darkmode>
	<h1>Welcome</h1>
	<div>
		I'm <strong>Andre Henriques</strong>; I am a software developer and designer who is currently
		studying at
		<a class="no-color-visited" href="https://www.surrey.ac.uk/undergraduate/computer-science"
			>Surrey University</a
		>
		and looking for a placement for the year 2022!
		<!-- To add placement-->
	</div>
	<div class="flex justify-center bigger-link">
		<a href="https://github.com/andr3h3nriqu3s11"> <!--github--> <span class="bi bi-github" /> </a>
		<span class="divider" />
		<a href="https://www.linkedin.com/in/andre-henriques-0240b1205/">
			<!-- linkedin --> <span class="bi bi-linkedin" /></a
		>
	</div>
	<div>
		<!-- To add cv-->
	</div>
</main>
<footer class="flex justify-center copy">
	<div>Copyrigth &copy; Andre Henriques 2021. All Rigths Reserved;</div>
</footer>

<svelte:head>
	<title>Andre Henriques</title>
	{#if darkmode}
		<style>
			body {
				background: #2a2a2a;
				color: white;
			}
		</style>
	{/if}
</svelte:head>

<style>
	:global(body) {
		padding: 0;
		margin: 0;
		display: grid;
		justify-content: center;
	}
	main {
		margin-top: 50px;
		width: 50vw;
		min-height: calc(100vh - 2rem - 50px);
	}
	.flex {
		display: flex;
	}
	.justify-center {
		justify-content: center;
	}
	h1 {
		font-size: 3rem;
	}
	div {
		font-size: 1.5rem;
		margin-top: 0.4rem;
	}
	.bigger-link {
		margin-top: 2rem;
		font-size: 2rem;
		color: #6d6f71;
	}
	.bigger-link a {
		transition: color 0.75s;
	}
	.bigger-link .divider {
		height: 2rem;
		margin: 0rem 1rem;
		border: 2px solid #6d6f71;
	}
	.bigger-link a:visited {
		font-size: 2rem;
		color: #6d6f71;
	}
	.bigger-link a:hover {
		font-size: 2rem;
		color: rgb(54, 55, 56);
		transition: color 0.25s;
	}
	.darkmode .bigger-link a:hover {
		font-size: 2rem;
		color: #bcbcbc;
		transition: color 0.25s;
	}
	.no-color-visited {
		color: rgb(14, 142, 185);
		text-decoration: none;
	}
	.no-color-visited:visited {
		color: rgb(14, 142, 185);
		text-decoration: none;
	}
	.no-color-visited:hover {
		color: rgb(8, 112, 160);
	}
	.copy div {
		font-size: 1rem;
	}
</style>
