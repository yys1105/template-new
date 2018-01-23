<script>
  import phone from './phone'
  import edit from './edit'
  export default {
    name: '',
    components:{phone,edit},
    data() {
      return {
        treeDom:[1]
      }
    },
    methods:{
      addModule(mode){
        if(mode===0){

        }
      }
    }
  }
</script>

<template>
  <div class="home">
    <div class="preview">
      <phone :data="treeDom"></phone>
    </div>
    <div class="edit">
      <edit @addModule="addModule"></edit>
    </div>
  </div>
</template>

<style scoped lang="stylus">
  .home
    display flex
    .edit
      flex 1
    .preview
      width 375px
      height 667px
      background-color #2a2955
</style>
