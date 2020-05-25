<script>
	import Dc from './dc.svelte';

	export let name;
	let src = 'https://media1.tenor.com/images/4a96d6c6ce310c9cc1b10b21ea327651/tenor.gif?itemid=14666652';
</script>

<main>
	<h1>Hola {name.toUpperCase()}!</h1>

	<img {src} alt="{name}">
</main>

<main>
	<Dc />
</main>

<style>
	main {
		text-align: center;
	}

	h1 {
		color: #ff3e00;
	}

</style>