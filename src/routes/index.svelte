<script lang="ts">
	import { onMount } from 'svelte';

	import '../css/generic.css';
	import ProfessionalWork from '../components/ProfessionalWork.svelte';
	import Intruduction from '../components/Intruduction.svelte';
	import Sidebar from '../components/Sidebar.svelte';
	import PersonalProjects from '../components/PersonalProjects.svelte';

	function isDarkModeEnabled() {
		if (typeof window !== 'undefined' && typeof window.matchMedia !== 'undefined') {
			return window.matchMedia('(prefers-color-scheme: dark)').matches;
		} else {
			//throw new Error('matchMedia is not supported');
			return false;
		}
	}

	let darkmode = false;

	onMount(() => {
		darkmode = isDarkModeEnabled();
	});

	let intruductionH = 0;
	let professionalH = 0;
	let personalH = 0;
</script>

<div class="fullw">
	<Sidebar
		items={[
			{ name: 'About me', link: '#about', height: intruductionH - 200 },
			{ name: 'Professional work', link: '#work', height: professionalH - 20 },
			{ name: 'Personal projects', link: '#personal', height: personalH }
		]}
		{darkmode}
	/>

	<button
		on:click={() => {
			darkmode = !darkmode;
		}}
		class="change-mode bigger-link"
	>
		{#if darkmode}
			<span class="bi bi-moon" />
		{:else}
			<span class="bi bi-sun" />
		{/if}
	</button>

	<main class:darkmode>
		<Intruduction bind:h={intruductionH} {darkmode} />
		<ProfessionalWork bind:h={professionalH} {darkmode} />
		<PersonalProjects {darkmode} bind:h={personalH} />
	</main>
	<footer class="flex justify-center copy">
		<div>Copyright &copy; Andre Henriques 2021. All Rights Reserved;</div>
	</footer>
</div>

<svelte:head>
	<title>Andre Henriques</title>
	{#if darkmode}
		<style>
			body {
				background: #2a2a2a;
				/*background: linear-gradient(90deg, rgba(0, 0, 0, 1) 0%, rgba(42, 42, 42, 1) 10%);*/
				color: white;
				transition: color 0.5s;
				transition: background 0.5s;
			}
		</style>
	{:else}
		<style>
			body {
				transition: color 0.5s;
				transition: background 0.5s;
			}
		</style>
	{/if}
</svelte:head>

<style>
	:global(body) {
		padding: 0;
		margin: 0;
		scroll-snap-type: y mandatory;
	}
	main {
		margin-top: -150px;
		min-height: calc(100vh - 2rem - 50px);
		display: grid;
		justify-content: center;
		width: 50vw;
	}
	.fullw {
		width: 99vw;
		display: grid;
		place-items: center;
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
	.copy div {
		font-size: 1rem;
	}
	.change-mode {
		position: absolute;
		right: 2rem;
		top: 0px;
		margin-top: 0.5rem;
		font-size: 1.5rem;
		outline: none;
		border: none;
		background: none;
	}
	@media only screen and (max-width: 500px) {
		:global(body) {
			text-align: center;
		}
		main {
			width: 98vw;
			min-height: calc(100vh - 2rem - 50px);
		}
	}
	@media only screen and (max-width: 1100px) {
		main {
			margin-top: 50px;
			width: 70vw;
			min-height: calc(100vh - 2rem - 50px);
		}
	}
</style>
