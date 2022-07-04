<script>
    import TodoItem from './TodoItem.svelte';

    export let fetchTodos;
    export let handleCheckTodo;
    export let handleRemoveTodo;
    export let editMode;
    export let handleChangeEditMode;
    export let handleEditTodoItem;
    export let handleEditInputKeyup;
</script>

<div class="main">
    <ul>
        {#each fetchTodos as todo, index (todo)}
            <li>
                <TodoItem
                    {todo}
                    {handleCheckTodo}
                    {handleRemoveTodo}
                    {editMode}
                    {handleChangeEditMode}
                    {handleEditTodoItem}
                    {handleEditInputKeyup}
                />
            </li>
        {/each}
    </ul>
</div>
