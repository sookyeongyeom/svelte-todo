<script>
    export let todo;
    export let handleCheckTodo;
    export let handleRemoveTodo;
    export let editMode;
    export let handleChangeEditMode;
    export let handleEditTodoItem;
    export let handleEditInputKeyup;
</script>

<input
    type="checkbox"
    bind:checked={todo.done}
    on:click={() => handleCheckTodo(todo.id)}
/>
{#if editMode === todo.id}
    <input
        type="text"
        bind:value={todo.content}
        on:focusout={() => handleEditTodoItem(todo)}
        on:keyup={(e) => handleEditInputKeyup(e, todo)}
    />
{:else}
    <span
        class:done={todo.done}
        on:dblclick={() => handleChangeEditMode(todo.id)}
    >
        {todo.content}
    </span>
{/if}
<!-- <span class:done={todo.done}>{todo.content}</span> -->
<!-- <span>{todo.done}</span> -->
<a href="#null" on:click={() => handleRemoveTodo(todo.id)}>X</a>
