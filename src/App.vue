<script setup lang="ts" >
import Fruit from './components/Fruit.vue';
</script>

<template>
  <Fruit v-for="value in Fruit" :key="value" />
</template>