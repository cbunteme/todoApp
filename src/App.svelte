<script>
	import Todos from './Todos.svelte';
</script>

<main>
	<h1>Organize Your Day</h1>
	<h2>Enter your todo list and check off the tasks as you go! You got this!</h2>
	<Todos />
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		font-family: 'Chonburi', cursive;
		color: #3A8878;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	h2 {
		font-size: 1.5em;
		font-family: 'Open Sans Condensed', sans-serif;
		margin-bottom: 2rem;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>