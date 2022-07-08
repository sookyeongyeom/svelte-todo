<script>
    import TodoItem from './TodoItem.svelte';
    import { fetchTodos } from '../store';
    import { fade, slide } from 'svelte/transition';
    import { flip } from 'svelte/animate';
</script>

<div class="main">
    <ul>
        {#each $fetchTodos as todo, index (todo)}
            <li
                in:fade
                out:slide={{ duration: 300 }}
                animate:flip={{ duration: 300 }}
            >
                <TodoItem {todo} />
            </li>
        {/each}
    </ul>
</div>
