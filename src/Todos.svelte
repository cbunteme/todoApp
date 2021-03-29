<script>
    import { fly } from 'svelte/transition';
    let todoItem = '';
    let todoList = [];
// add itmes from input field to array
    function addTodoList(){ 
        if (!todoItem) return;
        todoList = [...todoList, {
            text: todoItem,
            status: false
        }];
        todoItem = '';
    }
// remove items from array 
    function removeFromList(index) {
        todoList.splice(index, 1);
        todoList = todoList;
    }    
</script>

<form on:submit|preventDefault={addTodoList}>
    <input style="width: 400px;" class="input is-rounded" bind:value={todoItem}>
</form>

<ul class="list">
    {#each todoList as item, index}
    <li transition:fly="{{ y: 20, duration: 200 }}">
    <input bind:checked={item.status} class="checkbox" type="checkbox">
    <span class:checked={item.status}>{item.text}</span>
    <button class="delete is-medium" type="button" on:click={() => removeFromList(index)}></button>
    </li>
    {/each}
</ul>

<style>
    .list {
        list-style: none;
        font-size: 1.5rem;
    }
    .checked {
        text-decoration: line-through;
    }
    li {
        font-family: 'Open Sans Condensed', sans-serif;
    }
    button {
        margin-left: 2rem;
    }
</style>