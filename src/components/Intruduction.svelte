<script>
	import '../css/generic.css';
	export let darkmode = false;

	export let h = 0;
</script>

<section class="intro" id="about" class:darkmode bind:clientHeight={h}>
	<h1>Welcome</h1>
	<h2>Some information about me:</h2>
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
		<div class="h1 text-center" style="margin-bottom: 1.2rem;">
			Check if the version of my CV you have is the newest
		</div>
		<button on:click={() => window.open('/André_Henriques_CV.pdf', '_blank')}> View CV </button>
	</div>
</section>

<style>
	.intro {
		min-height: 100vh;
		scroll-snap-align: start;
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
	.h1 {
		font-size: 2rem;
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
</style>
