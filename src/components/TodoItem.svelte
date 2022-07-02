<script>
    export let todo;
    export let handleCheckTodo;
</script>

<input
    type=checkbox
    bind:checked="{todo.done}"
    on:click="{()=>handleCheckTodo(todo.id)}">
<span>{todo.content}</span>
<span>{todo.done}</span>