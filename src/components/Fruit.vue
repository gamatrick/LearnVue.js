<script setup lang="ts" >

import { ref, computed} from 'vue'



const model = ref(0)
const fruits: Fruit[] = [
  { name: 'apple', image: 'https://m.media-amazon.com/images/I/81Dl5GdAVkL.png' },
  { name: 'banana', image: 'https://upload.wikimedia.org/wikipedia/commons/2/2c/Banana_on_black_background.jpg' },
  { name: 'orange', image: 'https://media.istockphoto.com/id/477836156/fr/photo/orange-fruits-isol%C3%A9-sur-blanc.jpg?s=612x612&w=0&k=20&c=Qw_SKI4glq0hjhmvmRCoLsh27VWax5Bh7ehrzSSIQXE=' },
]

interface Fruit{
  name: string,
  image: string
}

const buttonupdate = computed((): Fruit => fruits[model.value % fruits.length]!)
const update = () => { model.value++ }

</script>

<template>
  <img :src="buttonupdate.image" :alt="buttonupdate.name" />
  <FruitButton :name="buttonupdate.name" @click="model" />
</template>

<style scoped>
img {
  width: 200px;
  height: 200px;
  object-fit: cover;
}
</style>
