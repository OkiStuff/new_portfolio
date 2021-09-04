<script>
	import router from "page"
	import home from "./components/home.svelte"
	import projects from "./components/projects.svelte"
	import skills from "./components/skills.svelte"
	import about from "./components/about.svelte"
	import contact from "./components/contact.svelte"
	
	let page;
	
	router('/', () => page = home);
	router('/projects', () => page = projects);
	router('/skills', () => page = skills);
	router('/about', () => page = about);
	router('/contact', () => page = contact);
	
	router.start();
	
	const redirect = (url) => {
		window.location.href = url;
	};
</script>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Fira+Code&display=swap" rel="stylesheet">

<header>
	<a href="/" class="link_home"><h1>Frankie A.</h1></a>
	<p>Game Engine Developer, Student Pilot</p>
</header>




<svelte:component this={page} />

<img src="./github.png" alt="github" class="footer" on:click={() => redirect("https://github.com/okistuff")}>


<style>
	header {
		text-align: center;
		color: white;
	}
	
	.footer {
		position: absolute;
		bottom:1%;
	}
	
	.footer:hover {
		filter: invert(100%);
		-webkit-filter: invert(100%);
		cursor:pointer;
		-webkit-transition: filter 200ms linear;
		-ms-transition: filter 200ms linear;
		transition: filter 200ms linear;
	}
	
	:root::-webkit-scrollbar {
		display: none;
	}
	
	:root {
		background-color: #2f4f4f;
	}
	
	* {
		margin: 0;
		padding: 0;
		/*font-family: 'Fira Code', monospace;*/
	}
	
	.link_home:link {
		color: white;
	}
	.link_home:visited {
		color: white;
	}
	.link_home:hover {
		color: white;
	}
	.link_home:active {
		color: white;
	}

</style>