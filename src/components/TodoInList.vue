<template>
    <ul>
        
        <TodoListItem v-for="todoItem in myData" :key="todoItem.id" :item="todoItem" />
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