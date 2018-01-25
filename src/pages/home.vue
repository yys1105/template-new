<script>
  import phone from './phone'
  export default {
    name: '',
    components:{phone},
    data() {
      return {
        form:{
          title:''
        }
      }
    },
    methods:{

    }
  }
</script>

<template>
  <div class="home">
    <div class="preview">
      <phone></phone>
    </div>
    <div class="edit">
      <el-form ref="form" :model="form" label-width="80px">
        <el-form-item label="标题">
          <el-input v-model="form.title"></el-input>
        </el-form-item>
      </el-form>
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
