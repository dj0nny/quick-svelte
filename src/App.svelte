<script>
	import { onMount } from 'svelte'

	let todos = []

	onMount(async() => {
		const res = await fetch('http://jsonplaceholder.typicode.com/todos')
		todos = await res.json()
	})

</script>

<style>

#header {
    display: flex;
    flex: 1;
    border-bottom: 1px solid #000;
}

.todos {
	margin-top: 50px;
}
.todo {
	display: inline-block;
	width: 33%;
	margin-bottom: 30px;
	text-align: center;
}

</style>

<div id="header">
	<h1>Quick Svelte</h1>
</div>

<div class="todos">
	{#each todos as todo}		
		<div class="todo">
			<div class="todo-name">
				{todo.title}
			</div>
			<div class="status">
				<input type="checkbox" bind:checked={todo.completed}>
			</div>
		</div>
	{/each}
</div>
