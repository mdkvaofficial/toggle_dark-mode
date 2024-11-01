<script lang="ts">
	import { onMount } from 'svelte';
	let isDarkMode = false;
	onMount(() => {
		isDarkMode = localStorage.getItem('dark-mode') === 'true';
		updateDarkMode();
	});
	function toggleDarkMode() {
		isDarkMode = !isDarkMode;
		localStorage.setItem('dark-mode', isDarkMode.toString());
		updateDarkMode();
	}
	function updateDarkMode() {
		document.body.classList.toggle('dark-mode', isDarkMode);
	}
</script>
<main>
	<h1>Assalaam-o-Alaekum!</h1>
	<p>May Allah Almighty Bless You. Ameen!</p>
<div>
	<button type="button" on:click={toggleDarkMode}>
		{isDarkMode ? 'Switch to Light Mode' : 'Switch to Dark Mode'}
	</button>
	
</div>
<br>
<p>The code in the file <b>"src/routes/+page.svelte"</b> allows dark mode toggle functionality.</p>
<br>
<p>This is designed particularly for <b>Sveltekit</b>. However, With some editting, the logic can be used for other frameworks as well.</p>
<br>
<p><b>Good Luck!</b></p>
</main>
<style>
	* {
		margin: 0;
		padding: 0;
		font-family: Arial, Helvetica, sans-serif;
	}
	:global(body) {
		background-color: white;
		color: black;
		transition:
			background-color 0.3s,
			color 0.3s;
	}
	:global(body.dark-mode) {
		background-color: black;
		color: white;
	}
	button {
		margin-top: 20px;
		padding: 10px 20px;
		cursor: pointer;
		font-size: 1em;
		background-color: red;
		color: white;
	}
	button:hover {
		background-color: rgba(255, 0, 0, 0.344);
		border: blue;
	}
	main{
		width: auto;
		margin-top: 20vh;
	}
	div{
text-align: center;
	}
</style>
