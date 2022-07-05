<template>
    <li>
        <span>{{ item.text }}</span>
        <button>Sil</button>
    </li>
</template>
<script>
export default {
    props: ["item"]
}
</script>
