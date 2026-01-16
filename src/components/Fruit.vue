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

function update() {
  model.value++ 
}

const buttonupdate = computed(()=> {
   return fruits[model.value%3]
})

</script>



<style scoped>
img {
  width: 200px;
  height: 200px;
  object-fit: cover;
}
</style>
