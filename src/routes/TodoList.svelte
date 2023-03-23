<script>
    import TodoItem from "./TodoItem.svelte";

    export let todoItems;

    $: todosCount = todoItems.length;

</script>

Number of todos: { todosCount }
<div class="todo-items">
    {#each todoItems as item}
        <TodoItem {...item} />
    {/each}

</div>

<style>
    .todo-items {
        border: 3px solid
    }
</style>