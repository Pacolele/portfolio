<script lang="ts">
	import '../css/reset.css';
	import '../css/nav.css';
	import { onMount } from 'svelte';
	import { afterNavigate } from '$app/navigation';

	// State to control the visibility of the menu
	let isNavActive = false;

	let currRoute = '/';

	// Function to toggle the menu
	function toggleNav() {
		isNavActive = !isNavActive;
	}

	onMount(() => {
		currRoute = window.location.pathname;
	});

	// @ts-ignore
	afterNavigate((event) => {
		currRoute = window.location.pathname;
	});
</script>

<nav class="navbar-fixed-top">
	<div class="logo">
		<img src="/images/portfoliologo.png" alt="logo" />
		<h1>Hernesten</h1>
	</div>
	<ul>
		<li>
			<a href="/" class={currRoute === '/' ? 'active-link' : ''}>Home</a>
		</li>
		<li>
			<a href="/projects" class={currRoute === '/projects' ? 'active-link' : ''}>Projects</a>
		</li>
		<li>
			<a href="/about" class={currRoute === '/about' ? 'active-link' : ''}>About</a>
		</li>
	</ul>
	<div class="hamburger {isNavActive ? 'hamburger-active' : ''}" on:click={toggleNav}>
		<span class="line"></span>
		<span class="line"></span>
		<span class="line"></span>
	</div>
</nav>
<div class="menubar {isNavActive ? 'active' : ''}">
	<ul>
		<li>
			<a href="/" on:click={toggleNav} class={currRoute === '/' ? 'active-link' : ''}>Home</a>
		</li>
		<li>
			<a
				href="/projects"
				on:click={toggleNav}
				class={currRoute === '/projects' ? 'active-link' : ''}>Projects</a
			>
		</li>
		<li>
			<a href="/about" on:click={toggleNav} class={currRoute === '/about' ? 'active-link' : ''}
				>About</a
			>
		</li>
	</ul>
</div>

<slot />

<style>
	@import url('https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap');
</style>
