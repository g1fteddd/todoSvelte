<script>
    import TodoItem from './TodoItem.svelte'
    let newTodo
    let todos = []


    const addTodo = () => {
        if (newTodo) {
            todos.push(newTodo)
            todos = todos
            newTodo = ''
        }
    }

    const handleKeyEnter = (event) => {
        event.code === "Enter" && addTodo()
    }

    const removeTodo = (event) => {
        todos.splice(event.detail, 1)
        todos = todos
    }

    $: todoLenght = todos.length
</script>

<div class="tl">
    <label for="input-todo">Название дела</label>
    <input on:keydown={handleKeyEnter} bind:value={newTodo} id="input-todo" type="text" placeholder="Начните печатать...">
    
    {#each todos as todo, i}
        <TodoItem on:remove={removeTodo} todo="{todo}" index="{i}"/>
    {/each}

    <button on:click={addTodo}>Добавить дело</button>
    <span>Количество дел: {todoLenght}</span>
</div>

<style>
    .tl {
        text-align: left;
        width: 400px;
        margin: auto;
        display: grid;
        grid-gap: 12px;
    }
</style>