<script>
	import TodoList from "./TodoList.svelte";
	export let name;
</script>

<main>
	<h1>Список {name}!</h1>
	<TodoList/>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

</style>