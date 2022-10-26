<script lang="ts">
	import Fa from 'svelte-fa';
	import { faMoon, faSun } from '@fortawesome/free-solid-svg-icons';
	import { onMount } from 'svelte';
	import { fade } from 'svelte/transition';

	export let btnClass = '';

	let currentTheme: string;

	const setTheme = (theme: string) => {
		currentTheme = theme;
		document.documentElement.setAttribute('data-theme', theme);
	};

	const toggleTheme = () => {
		const newTheme = currentTheme === 'light' ? 'dark' : 'light';
		setTheme(newTheme);
		localStorage.setItem('theme', newTheme);
	};

	onMount(() => {
		currentTheme =
			localStorage.getItem('theme') ||
			(window.matchMedia('(prefers-color-scheme: dark)').matches ? 'dark' : 'light');
		setTheme(currentTheme);
	});
</script>

<button on:click={toggleTheme} aria-label="Toggle theme" class={`btn btn-ghost ${btnClass}`}>
	{#if currentTheme === 'light'}
		<span in:fade>
			<Fa icon={faMoon} fw />
		</span>
	{:else}
		<span in:fade>
			<Fa icon={faSun} fw />
		</span>
	{/if}
</button>
