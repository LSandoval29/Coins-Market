<template>
  <button class="mt-5 p-2 btn btn-primary" @click="accion">{{ texto }}</button>
</template>

<script>
export default {
    props:{
        texto:String
    },
    methods:{
        accion() {
            this.$emit('accion')
        }
    }
}
</script>

<style>

</style>