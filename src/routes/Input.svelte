<script>
    import { createEventDispatcher } from "svelte";

    const dispatch = createEventDispatcher();

    let newItemName;

    function handleAddClick(event) {
        console.log(newItemName);
        dispatch('newItem', {
            name: newItemName
        })
    }

</script>

<div>
    <input type="text" bind:value={newItemName} /> <button on:click={handleAddClick}>Add</button>
</div>