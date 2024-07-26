<script>

export default {
    data() {
        return {
            newTask: '',
        }
    },
    emits: ['addData'],
    methods: {
        addTask(e) {
            this.$emit('addData', this.newTask)
            this.newTask = ''
        }
    }
}
</script>

<template>
    <form class="form-m" @submit.prevent="addTask">
        <label for="task">Tugas</label>
        <input type="text" v-model="newTask" id="task">
        <button type="submit" >Tambah</button>
    </form>
    <h1>{{task}}</h1>
</template>