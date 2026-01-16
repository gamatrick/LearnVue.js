<script setup lang="ts" >

defineProps<{ name: string 
    count : number
}>()
const emit = defineEmits<{ click: [] }>()

</script>

<template>
    <p>count : {{count}}</p>
    <button @click="emit('click')">fruit :{{name }} </button>
</template>
