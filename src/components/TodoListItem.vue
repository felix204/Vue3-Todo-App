<template>
    <li>
        <span>{{ item.text }}</span>
        <button @click="$emit('delete-todo-item', item)">Sil</button>
    </li>
</template>
<script>
export default {
    props: ["item"]
}
</script>
