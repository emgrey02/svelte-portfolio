<script lang="js">
	import Bio from './components/Bio.svelte';
	import Footer from './components/Footer.svelte';
	import Project from './components/Project.svelte';
	import ProjectContainer from './components/ProjectContainer.svelte';

	const projects = [
		{
			title: "Harmonic Presence",
			link: "https://harmonicpresence.netlify.app",
			image: "https://res.cloudinary.com/greypse/image/upload/c_scale,r_0,w_500/v1644447893/harm-pres_wmhy4q.png",
			description: "An interactive multimedia presentation experienced through the browser. Made for large devices. Its purpose is to educate and inform people about the existence of harmonics.",
			technologies: ['Pixi.js', 'Typescript', 'HTML/CSS', 'Netlify', 'Webpack'],
			code: "https://github.com/emgrey02/harmonic-presence-pres"
		},
		{
			title: "Utter Nonsense",
			link: "https://duck-stanza-emgrey02.netlify.app",
			image: "https://res.cloudinary.com/greypse/image/upload/v1646856568/duck-display_rkxwzw.png",
			description: "A responsive website that displays a poem by Edward Lear and an image. Also included is an option for the user to choose a color theme - dark, light, or system.",
			technologies: ['Javascript', 'Sass', 'HTML/CSS', 'Parcel'],
			code: 'http://github.com/emgrey02/utter-nonsense-emgrey02'
		}
	]
</script>

<main>
	<Bio/>
	<ProjectContainer>
		{#each projects as project}
			<Project {...project}/>
		{/each}
	</ProjectContainer>
	<Footer/>
</main>

<style>
	
	
</style>