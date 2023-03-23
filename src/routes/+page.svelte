<script>
    import Input from './Input.svelte';
    import TodoList from './TodoList.svelte';

    let todoItems = [
        {"completed": false, "text": "Learn Svelte"}, // 0
        {"completed": false, "text": "Make Toast"},    // 1
        {"completed": true, "text": "Make Coffee"}
    ]

    let newItemName;

    function handleNewItem(event) {
        newItemName = event.detail.name;
        addNewItem();
    }

    function addNewItem() {
        let newItem  = {"completed": false, "text": newItemName};
        todoItems = [...todoItems, newItem]
    }
</script>

<h1>Todo App Class Activity</h1>

<Input on:newItem={handleNewItem}/>

<TodoList todoItems={todoItems} />

