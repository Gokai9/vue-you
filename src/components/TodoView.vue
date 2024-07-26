<script>
import TodoInput from './TodoInput.vue';
import TodoList from './TodoList.vue';
let id = 0
export default {
    components: {
        TodoInput, TodoList
    },
    data() {
        return {
            todos: [
                {id: id++, task: "samba"}
            ]
        }
    },
    methods: {
        addTask(task) {
            this.todos.push({id: id++, task})
        }
    }
}
</script>

<template>
    <div v-if="todos.length > 0">
        <ul v-for="todo in todos">
            <TodoList :todo="todo"/>
        </ul>
    </div>
    
    <TodoInput @addData="addTask"/>
</template>