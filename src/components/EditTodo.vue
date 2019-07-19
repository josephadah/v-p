<template>
    <form @submit.prevent="editTodo">
        <div class="form-row mb-4">
            <h4 class="pr-2">Edit Todo: </h4>
            <div class="col">
                <input type="text" v-model="todo.title" class="form-control">
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
    name: 'EditTodo',
    props: {
        todo: Object
    },
    methods: {
        editTodo() {
            if (todo.title) {
                this.$emit('edit-todo', this.todo);
            }
        }
    }
}
</script>

