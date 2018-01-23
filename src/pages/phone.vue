<script>
  export default {
    name: '',
    props:{
      data:{
        type:Array
      }
    },
    data() {
      return {}
    }
  }
</script>

<template>
  <div>
    <template v-for="item in data">
      {{item}}
    </template>
  </div>
</template>


<style scoped>

</style>
