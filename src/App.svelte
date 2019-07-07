<script>
import Todo from './components/Todo.svelte'
import Header from './components/Header.svelte'


import { onMount } from 'svelte'

let todos = []
let done
let undone

onMount(async() => {
	const res = await fetch('https://jsonplaceholder.typicode.com/todos')
	todos = await res.json()
	done = todos.filter((todo) => todo.completed).length
	undone = todos.filter((todo) => !todo.completed).length
})

</script>

<style>
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

<Header appTitle="Quick Svelte" done={done} undone={undone}></Header>
<div class="todos">
	{#each todos as todo}		
		<div class="todo">
			<Todo todo={todo}></Todo>
		</div>
	{/each}
</div>
