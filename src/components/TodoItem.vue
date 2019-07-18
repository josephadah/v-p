<template>
    <div>
        <p>{{todo.id}} {{todo.title}} {{todo.completed}}</p>
    </div>
</template>

<script>
export default {
    name: "TodoItem",
    props: {
        todo: Object
    }
}
</script>

<style>

</style>


