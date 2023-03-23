<script>
    import TodoItem from "./TodoItem.svelte";

    let todoItems = [
        {"completed": false, "text": "Learn Svelte"}, // 0
        {"completed": false, "text": "Make Toast"},    // 1
        {"completed": true, "text": "Make Coffee"}
    ]

    $: todosCount = todoItems.length;

    function addButtonClickHandler() {
        if (document.getElementById("inp-todoText").value) {
            let newItemtext = document.getElementById("inp-todoText").value;
            let newItem  = {"completed": false, "text": newItemtext};

            document.getElementById("inp-todoText").value = '';

            todoItems = [...todoItems, newItem]
        }
    }
</script>

<div>
    <input id="inp-todoText" type="text" /> <button on:click={addButtonClickHandler}>Add</button>
</div>

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