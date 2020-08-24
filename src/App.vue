<template>
<p class="bg-blue-500 bg-opacity-100 text-6xl uppercase">hello world</p>
 <fly to="full">
   teleport full screen
 </fly>
</template>

<script>
import fly from './components/fly.vue'

export default {
  name: 'App',
  components: {
    fly
  }
}
</script>
