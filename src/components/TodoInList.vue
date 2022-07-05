<template>
    <ul>
        
        <TodoListItem @delete-todo-item="$emit('delete-todo-item', $event)" v-for="todoItem in myData" :key="todoItem.id" :item="todoItem" />
    </ul>
</template>

<script>
    import TodoListItem from "@/components/TodoListItem.vue";
    export default {
        props : ["myData"],
        components : {
            TodoListItem,
        }
    }
</script>