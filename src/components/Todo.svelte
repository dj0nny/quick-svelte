<script>
export let todo
</script>

<div class="todo-wrapper">
  <div class="todo-name">
				{todo.title}
  </div>
  <div class="todo-status">
    <input type="checkbox" disabled bind:checked={todo.completed}>
  </div>
</div>