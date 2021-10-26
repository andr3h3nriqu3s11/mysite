<script>
	import ProfessionalWorkItem from './ProfessionalWorkItem.svelte';

	export let darkmode;
	export let h;
</script>

<section id="work" bind:clientHeight={h}>
	<div class="h1 text-center" style="margin-bottom: 1.2rem;">Professional Work</div>
	<!-- Profecional work items -->
	<div class="flex space-around wrap">
		<ProfessionalWorkItem
			{darkmode}
			link="https://usenumo.com.br/"
			faviconLink="https://usenumo.com.br/assets/img/favicon111.png"
			title="Numo"
		>
			Benefits platform for employees of affiliated companies.
		</ProfessionalWorkItem>
		<ProfessionalWorkItem
			{darkmode}
			link="https://drplay.com.br/"
			faviconLink="https://drplay.com.br/favicon.png"
			title="Dr Play"
		>
			Medical support services and telemedicine platform
		</ProfessionalWorkItem>
		<ProfessionalWorkItem
			{darkmode}
			link="https://drmoz.usenumo.com.br/"
			faviconLink="https://drmoz.usenumo.com.br/favicon.png"
			title="Dr Moz"
		>
			Medical support services and telemedicine platform
		</ProfessionalWorkItem>
		<ProfessionalWorkItem
			{darkmode}
			link="https://icargo.usenumo.com.br/"
			faviconLink="https://icargo.usenumo.com.br/assets/img/favicon_icargo.png"
			title="Icargo"
		>
			Platform that links truck drivers and companies
		</ProfessionalWorkItem>
	</div>
</section>

<style>
	div {
		font-size: 1.5rem;
		margin-top: 0.4rem;
	}
	.h1 {
		font-size: 2rem;
	}
	section {
		margin-top: 20px;
		min-height: 100vh;
	}
	@media only screen and (max-width: 500px) {
		section .h1 {
			display: block;
		}
	}
</style>
