<script>
  import tools from '../components/tools'
  export default {
    name: '',
    components:{tools},
    data() {
      return {}
    },
    methods:{
      addModule(mode){
        console.log(mode)
      }
    }
  }
</script>

<template>
  <div>
    <tools @addModule="addModule"></tools>
  </div>
</template>


<style scoped>

</style>
