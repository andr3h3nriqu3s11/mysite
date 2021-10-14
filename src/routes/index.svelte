<script lang="ts">
	import HideShow from '../components/HideShow.svelte';
	import { onMount } from 'svelte';

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
</script>

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
	<h1>Welcome</h1>
	<div>
		I am <strong>Andre Henriques</strong>; I am a software developer and designer who is currently
		studying at
		<a class="no-color-visited" href="https://www.surrey.ac.uk/undergraduate/computer-science"
			>Surrey University</a
		>
		and looking for a placement for the year 2022! <br />
		<br />
		You can contact
		<a class="no-color-visited" href="mailto:andr3h3nriqu3s@gmail.com">by email</a>.
	</div>
	<div class="flex justify-center bigger-link">
		<a href="https://github.com/andr3h3nriqu3s11"> <!--github--> <span class="bi bi-github" /> </a>
		<span class="divider" />
		<a href="https://www.linkedin.com/in/andre-henriques-0240b1205/">
			<!-- linkedin --> <span class="bi bi-linkedin" /></a
		>
	</div>
	<div class="center-btt">
		<button on:click={() => window.open('https://andr3h3nriqu3s.com/CV.pdf', '_blank')}>
			Resume
		</button>
		<!-- To add cv-->
	</div>
	<div class="segment">
		<span class="h1">Currently working on</span>
		<HideShow>
			<div class="inside">
				<div class="h2">Personal projects that I am working on rigth now:</div>
				<div class="inside">
					<div class="space">
						<a class="no-color-visited" href="https://github.com/andr3h3nriqu3s11/todoapp">
							Todo App
						</a> - A todo app with some game elements for android app written in flutter
					</div>
					<div class="space">
						<a class="no-color-visited" href="https://github.com/andr3h3nriqu3s11/timeprocess">
							Timeprocess
						</a> - A simple command line utility that works like a clocking out/in system
					</div>
					<div class="space">
						<a class="no-color-visited" href="https://github.com/andr3h3nriqu3s11/mysite">
							This Website
						</a> - Well... this Website
					</div>
				</div>
			</div>
		</HideShow>
	</div>
	<div class="segment">
		<span class="h1">Completed experiments</span>
		<HideShow>
			<div class="inside">
				<div class="h2">
					Small projects that I used to test out a technology or a language, but that are now mostly
					finished!
				</div>
				<div class="inside">
					<div class="space">
						<a class="no-color-visited" href="https://github.com/andr3h3nriqu3s11/humming-detector">
							Frequency detector
						</a> - A simple program written in rust that uses a Fourier transform to separate audio into
						multiple frequencies
					</div>
					<div class="space">
						<a class="no-color-visited" href="https://github.com/andr3h3nriqu3s11/pen-trainer">
							Pen trainer
						</a> - A simple program written in Go to help me get used to a graphic table that I got
					</div>
					<div class="space">
						<a class="no-color-visited" href="https://github.com/andr3h3nriqu3s11/tube-solver">
							Tube Solver
						</a> - A simple command tool utility to solve the tube sort style games written in C
					</div>
				</div>
			</div>
		</HideShow>
	</div>
	<div class="segment">
		<span class="h1">What I want to try out?</span>
		<HideShow>
			<div class="inside">
				<div class="h2">
					Areas that I want to explore but haven't had the time to try out, and how I plan to try
					them out:
				</div>
				<div class="inside">
					<div class="space">
						Machine Learning - Train an AI to recognize my voice and what I say
					</div>
					<div class="space">VR - Create a simple game</div>
				</div>
			</div></HideShow
		>
	</div>
</main>
<footer class="flex justify-center copy">
	<div>Copyright &copy; Andre Henriques 2021. All Rights Reserved;</div>
</footer>

<svelte:head>
	<title>Andre Henriques</title>
	{#if darkmode}
		<style>
			body {
				background: #2a2a2a;
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
	:root {
		--c--blue: rgb(14, 142, 185);
		--c--blue-darker: rgb(8, 112, 160);
	}
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
		color: #6d6f71;
	}
	.darkmode .bigger-link a {
		color: black;
	}
	.bigger-link .divider {
		height: 2rem;
		margin: 0rem 1rem;
		border: 2px solid #6d6f71;
		background-color: #6d6f71;
	}
	.bigger-link a:visited {
		font-size: 2rem;
		color: #6d6f71;
	}
	:global(.bigger-link a:hover) {
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
	.h1 {
		font-size: 2rem;
	}
	.h2 {
		font-size: 1.5rem;
	}
	.segment {
		margin-top: 20px;
	}
	.segment .inside {
		margin-left: 2ch;
	}
	.segment .space {
		margin: 20px 0px;
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
	.center-btt {
		display: grid;
		place-items: center;
		margin-top: 1rem;
	}
	.center-btt button {
		background-color: var(--c--blue);
		color: white;
		font-size: 1.25rem;
		padding: 0.5em;
		border: none;
		outline: none;
		border-radius: 5px;
		box-shadow: 2px 2px 10px rgb(53, 53, 53);
		transition: background-color 0.5s;
	}
	.center-btt button:hover {
		background-color: var(--c--blue-darker);
		transition: background-color 0.5s;
	}
	@media only screen and (max-width: 500px) {
		:global(body) {
			text-align: center;
		}
		main {
			margin-top: 50px;
			width: 98vw;
			min-height: calc(100vh - 2rem - 50px);
		}
		.segment .h1 {
			display: block;
		}
		.segment .inside {
			margin-left: 0px;
		}
	}
</style>
