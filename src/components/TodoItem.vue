<template>
    <div class="todo-item">
        <p>{{todo.title}}</p>
    </div>
</template>

<script>
export default {
    name: 'TodoItem',
    props: {
        todo: Object
    }
}
</script>

<style lang="css" scoped>
    .todo-item {
        padding: 5px 20px;
        border-radius: 10px;
        border: 1px solid #DDD;
        margin-bottom: 10px;
    }
</style>