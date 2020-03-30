<template>
    <form @submit="addTodo">
        <input name="task" v-model="task" placeholder="Add todo..." type="text">
        <input type="submit" value="submit">
    </form>
</template>

<script>
import {v4 as uuidv4} from 'uuid';
export default {
    name: 'AddTodo',
    data() {
        return {
            task: ''
        }
        
    },
    methods: {
        addTodo(e) {
            e.preventDefault();
        const newTodo = {
            id: uuidv4(),
            task: this.task,
            completed: false
        }-
        this.$emit=('a-todo', newTodo)
        }

    }
}
</script>

<style scoped>
form {
    display: flex;
    padding: 0.5rem;
}


input {
    padding: 0.2rem;
    padding-left: 2rem;
    flex: 1;
    margin-left: 4rem;
}

</style>