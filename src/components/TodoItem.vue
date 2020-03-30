<template>
    <div class="todo-style" v-bind:class="{'task-completed': todo.completed}">
        <p>
            <input @change="markcomplete" class="checkbox-style" type="checkbox">
            <span class="task-style">{{todo.task}}</span>
            <button class="button-icon" v-on:click="$emit('del-todo', todo.id)">
                <i class="far fa-times-circle"></i></button>
            </p>
    </div>
</template>

<script>
export default {
    name: "TodoItem",
    props: ["todo"],
    methods: {
        markcomplete(){
            this.todo.completed = !this.todo.completed;
        },
       
    }
    
}
</script>

<style scoped>
.task-completed {
    text-decoration: line-through;
}
button {
    background: none;
    border: none; 
    justify-content: center;
}

.fa-times-circle {
    color: red;
}
input {
    margin-left: 4rem;
}
span {
    margin-left: 2rem;
}

.todo-style {
    display: flex;
    background-color: lightgray;
    padding: 0.5rem;
    border-bottom: 1px whitesmoke dotted;
    font-weight: bold;
    flex-basis: 100%;
}
</style>