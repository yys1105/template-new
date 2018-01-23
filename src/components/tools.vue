<script>
  export default {
    name: '',
    data() {
      return {}
    },
    methods:{
      addModule(mode){
        this.$emit('addModule',mode)
      }
    }
  }
</script>

<template>
  <el-menu class="el-menu-demo" mode="horizontal">
    <el-submenu index="1">
      <template slot="title">新增模块</template>
      <el-menu-item index="1-1">
        <span @click="addModule(1)">有标题</span>
      </el-menu-item>
      <el-menu-item index="1-2">
        <span @click="addModule(0)">无标题</span>
      </el-menu-item>
    </el-submenu>
  </el-menu>
</template>

<style scoped lang="stylus">
</style>
