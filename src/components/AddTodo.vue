<template>
    <form @submit.prevent="addTodo">
        <div class="form-row mb-4">
            <h4 class="pr-2">Add Todo: </h4>
            <div class="col">
                <input type="text" v-model="title" class="form-control" placeholder="Enter Todo ...">
            </div>
            <div class="col">
                <button type="submit" class="btn btn-primary">Save</button>
            </div>
        </div>
    </form>
</template>

<script>
import uuid from 'uuid';

export default {
    name: 'AddTodo',
    data() {
        return {
            title: ''
        }
    },
    methods: {
        addTodo() {
            if (this.title) {
                const todo = {id: uuid.v4(), title: this.title, completed: false};
                this.$emit('add-todo', todo);
                this.title = '';
            }
        }
    }
}
</script>

