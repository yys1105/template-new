<script>
  import phone from './phone'

  export default {
    name: '',
    components: {phone},
    data() {
      return {
        title: '大',
        sections: [
          {
            title: {
              type: '0',
              value: '小'
            },
            contents: [{
              type: '0',
              value: '内'
            }]
          }
        ],
        titleOptions: [{
          value: '0',
          label: '无特殊样式'
        }, {
          value: '1',
          label: '绿色标题'
        }, {
          value: '2',
          label: '红色标题'
        }, {
          value: '3',
          label: '一级大标题'
        }],
        contentOptions: [{
          value: '0',
          label: '无特殊样式'
        }, {
          value: '1',
          label: '备注类型'
        }],
        dom:''
      }
    },
    methods: {
      addDiv(item) {
        item.contents.push({
          type: '0',
          value: ''
        })
      },
      deleteDiv(item,index){
        item.contents = [].concat(item.contents.slice(0,index),item.contents.slice(index+1,item.contents.length))
      },
      addSection(){
        this.sections.push({
          title: {
            type: '0',
            value: ''
          },
          contents: [{
            type: '0',
            value: ''
          }]
        })
      },
      createElement(){
        var preImgPath = '/static/images'
        var dom = ''
        dom = `<div class="card">
                <div class="header">
                  <div class="icon">
                    <img src="${preImgPath}/rep_bullet.png">
                  </div>
                  <div class="title">
                    ${this.title}
                  </div>
                  </div>${createCardElement(this.sections,dom)}</div>`
        console.log(dom)
        this.dom += dom
        function createCardElement(sections,sectionsElementString) {
          for(var i of sections){
            var divString = ''
            divString = createDivElement(i.contents,divString)
            sectionsElementString+=`<div class="content">
                                      <div class="section">
                                        <div class="title">${i.title.value}</div>
                                        ${divString}
                                      </div>
                                    </div>`
          }
          return sectionsElementString
        }
        function createDivElement(values,DivsElementString) {
          for(var i of values){
            DivsElementString+=`<div>${i.value}</div>`
          }
          return DivsElementString
        }
      },
      recall(){
        this.$refs.phone.recall()
      }
    }
  }
</script>

<template>
  <div class="home">
    <div class="preview">
      <phone :dom="dom" ref="phone"></phone>
    </div>
    <div class="edit">
      <el-card class="box-card">
        <div slot="header" class="clearfix">
          <el-input v-model="title" placeholder="请输入内容"></el-input>
        </div>
        <div>
          <div class="section" v-for="item in sections">
            <div class="label">
              <el-select class="select" size="small" v-model="item.title.type" placeholder="请选择">
                <el-option
                  v-for="item in titleOptions"
                  :key="item.value"
                  :label="item.label"
                  :value="item.value">
                </el-option>
              </el-select>
              <el-input class="input" v-model="item.title.value" size="small" placeholder="请输入段落标题"></el-input>
            </div>
            <div class="label" v-for="(div,key,index) in item.contents">
              <el-select class="select" size="large" v-model="div.type" placeholder="请选择">
                <el-option
                  v-for="item in contentOptions"
                  :key="item.value"
                  :label="item.label"
                  :value="item.value">
                </el-option>
              </el-select>
              <el-input v-model="div.value" placeholder="请输入段落内容"></el-input>
              <el-button type="danger" icon="el-icon-circle-close" plain @click="deleteDiv(item,key)"> </el-button>
            </div>
            <div class="add-button" @click="addDiv(item)">+点击增加一个div</div>
          </div>
          <div class="section">
            <div class="add-button" @click="addSection">+点击增加一个段落</div>
          </div>
        </div>
        <div class="button-wrap">
          <el-button type="primary" @click="createElement">立即创建</el-button>
          <el-button>清空</el-button>
          <el-button type="warning" @click="recall">撤回</el-button>
        </div>
      </el-card>
    </div>
  </div>
</template>

<style scoped lang="stylus">
  .home
    display flex
    height 100%
    .edit
      flex 1
      height 100%
      overflow auto
    .preview
      width 375px
      height 667px
      overflow auto
      background-color #2a2955

  .label
    display flex

  .section + .section
    margin-top 20px
    padding-top 20px
    border-top 2px dashed #409EFF

  .add-button
    border-radius 8px
    padding 8px
    border 1px dashed #409EFF
    text-align center
    color #409EFF
    cursor pointer
    font-size 14px
  .button-wrap
    padding 8px
</style>
