<script>
    export let todo;
    export let handleCheckTodo;
    export let handleRemoveTodo;
</script>

<input
    type="checkbox"
    bind:checked={todo.done}
    on:click={() => handleCheckTodo(todo.id)}
/>
<span class:done={todo.done}>{todo.content}</span>
<!-- <span>{todo.done}</span> -->
<a href="#null" on:click={() => handleRemoveTodo(todo.id)}>X</a>
