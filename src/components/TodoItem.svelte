<script>
    import { todos } from '../store';

    export let todo;

    const handleCheckTodo = () => todos.checkTodo(todo.id);
    const handleChangeTodoEditMode = () => todos.changeTodoEditMode(todo.id);
    const handleEditTodo = () => {
        todos.editTodo(todo);
        todos.closeTodoEditMode();
    };
    const handleRemoveTodo = () => todos.removeTodo(todo.id);
</script>

<input type="checkbox" bind:checked={todo.done} on:click={handleCheckTodo} />
{#if $todos.editMode === todo.id}
    <input type="text" bind:value={todo.content} on:focusout={handleEditTodo} />
{:else}
    <span class:done={todo.done} on:dblclick={handleChangeTodoEditMode}>
        {todo.content}
    </span>
{/if}
<!-- <span class:done={todo.done}>{todo.content}</span> -->
<!-- <span>{todo.done}</span> -->
<a href="#null" on:click={handleRemoveTodo}>X</a>
