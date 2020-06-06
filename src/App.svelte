<script>
	import Content from './Content.svelte'
	export let title;
</script>

<main>
	<h1>{title}</h1>
	<h3>Entre les tâches à exécuter une par une. Clique ensuite sur chaque élément terminé.</h3>

	<Content>

<h3>Tu peux vider la liste une fois que tu n'en as plus besoin</h3>
	</Content>


	<!-- <p>Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn how to build Svelte apps.</p> -->
</main>

<style>
	main {

		text-align: justify;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>