<script>
    import TodoItem from './TodoItem.svelte';
    import { fade, slide } from 'svelte/transition';
    import { flip } from 'svelte/animate';

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
            <li
                in:fade
                out:slide={{ duration: 300 }}
                animate:flip={{ duration: 300 }}
            >
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
