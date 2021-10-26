<script lang="ts">
	import '../css/generic.css';
	import HideShow from './HideShow.svelte';

	function isDarkModeEnabled() {
		if (typeof window !== 'undefined' && typeof window.matchMedia !== 'undefined') {
			return window.matchMedia('(prefers-color-scheme: dark)').matches;
		} else {
			//throw new Error('matchMedia is not supported');
			return false;
		}
	}

	export let darkmode: boolean;
	export let h = 0;
</script>

<div class:darkmode id="personal" bind:clientHeight={h}>
	<div class="segment">
		<span class="h1">Currently working on</span>
		<HideShow startShow>
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
		<HideShow startShow>
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
		<HideShow startShow>
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
</div>

<style>
	#personal {
		display: grid;
		grid-template-rows: auto auto auto 1fr;
		min-height: 100vh;
	}
	div {
		font-size: 1.5rem;
		margin-top: 0.4rem;
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
	@media only screen and (max-width: 500px) {
		.segment .h1 {
			display: block;
		}
		.segment .inside {
			margin-left: 0px;
		}
	}
</style>
