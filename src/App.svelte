<script lang="js">
	import Bio from './components/Bio.svelte';
	import Footer from './components/Footer.svelte';
	import Project from './components/Project.svelte';
	import ProjectContainer from './components/ProjectContainer.svelte';

	const projects = [
		{
			title: "Harmonic Presence",
			link: "https://harmonicpresence.netlify.app",
			image: "https://res.cloudinary.com/greypse/image/upload/c_thumb,w_400,g_face/v1644447893/harm-pres_wmhy4q.png",
			description: "An interactive multimedia presentation experienced through the browser. Made for large devices. Its purpose is to educate and inform anyone who's curious about the existence of harmonics.",
			technologies: ['Pixi.js', 'Typescript', 'Html/CSS', 'Netlify', 'Webpack'],
			code: "https://github.com/emgrey02/harmonic-presence-pres"
		},
		{
			title: "Another Site",
			link: "https://alskdfa;lskdf;akdjf",
			image: ";laksjd;flkasjdf",
			description: "hi there wowowoowowow",
			technologies: ['Svelte', 'Sass', 'rollup', 'html'],
			code: 'a;sldkfja;lsdkfja;lsdkfja;lsdkfjad'
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