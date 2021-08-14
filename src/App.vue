<template>
  <div class="container mt-5 text-center">
    <coins/>
  </div>
</template>

<script>
import Coins from './components/Coins.vue'
import Cuenta from './components/Cuenta.vue'

export default {
  name: 'App',
  components: {
    Cuenta,
    Coins
  },
  
}
</script>

<style>

</style>
