<template>
    <tr :class="todo.completed ? 'table-success' : ''">
        <th>{{ index + 1 }}</th>
        <td>{{todo.title}}</td>
        <td><span class="btn btn-primary" @click="$emit('toggle-completed', todo)">Complete</span></td>
        <td><span class="btn btn-secondary" @click="$emit('edit-todo', todo)">Edit</span></td>
        <td><span class="btn btn-danger" @click="$emit('delete-todo', todo)">Delete</span></td>
    </tr>
</template>

<script>
export default {
    name: "TodoItem",
    props: {
        todo: Object,
        index: Number
    }
}
</script>

<style>

</style>


