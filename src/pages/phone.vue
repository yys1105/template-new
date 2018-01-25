<script>
  export default {
    name: '',
    props:{
      dom:{
        type:String
      }
    },
    watch:{
      dom:function(val,oldVal){
        if(val!==oldVal){
          this.oldDom.push(oldVal)
        }
        var vdom = document.getElementById("dom")
        vdom.innerHTML = val
      }
    },
    data() {
      return {
        oldDom:[],
        recallIndex:0
      }
    },
    methods:{
      recall(){
        this.dom = this.oldDom.reverse().slice(this.recallIndex,this.recallIndex+1)[0]
      }
    }
  }
</script>

<template>
  <div class="bg-color">
    <div class="main-content">
      <div class="card wel-card">
        <div class="content">
          <div class="section wel-words">
            尊敬的××（先生/女士）：
          </div>
          <div class="section">
            您好！十分荣幸您选择我们为康基因公司为您进行本次基因检测服务！
          </div>
          <div class="section">
            我们很高兴为您提供此次检测的个性化基因检测报告，本检测对相关疾病的发生风险进行全面评估，由专业遗传学专家对您的疾病风险及生活习惯给予详细的解读和相应的健康指导，本次检测所涉及的DNA来自您最新提供的采集样本，检测内容有专业科学依据。本检测利用目前行业内先进的基因检测技术，准确获取相关位点基因型，从基因水平上对疾病的发生进行早期预测。
          </div>
          <div class="section">
            基于您的基因检测信息，我们提供个性化健康指导：
            <div>一、疾病预测——在健康或亚健康时能准确预测患病易感风险</div>
            <div>二、疾病预防——主动调节外因（饮食/运动/生活习惯/环境），降低患病风险</div>
            <div>三、健康管理——优化常规检查方案，提供自身健康管理方案</div>
          </div>
          <div class="section">
            根据世界卫生组织（WHO）报告，通过健康的生活方式，如戒烟、戒酒、运动和均衡饮食习惯以及有效运用当今的医疗手段（如定期筛检和早期检测），至少有50%以上的疾病是可以预防或避免的。针对相关疾病高风险的人群，我们会建议您加强对相关疾病的关注和认知，尽早开展相关健康检查，将患病风险控制在最低水平。
          </div>
          <div class="section">
            鉴于疾病发生机理的复杂性，当前医学对某些疾病的遗传基础认识的局限性及疾病的个体差异，我们不排除某些受检者有漏检的易感基因或致病变异位点。本检测报告仅供参考，不做临床诊断意见。
          </div>
        </div>
      </div>
      <div id="dom">

      </div>
    </div>
  </div>
</template>


<style>
  * {
    padding: 0;
    margin: 0;
  }
  html {
    line-height: initial;
    font-size: 100px;
  }
  body {
    font-size: 0.14rem;
  }
  .bg-color{
    background-color: #2a2955;
  }
  .main-content{
    padding: 0 .09rem .25rem .09rem;
  }
  .card{
    border-radius: .04rem;
    background-color: #fff;
  }
  .wel-card{
    background-color: #06a7f8;
  }
  .card{
    margin-top: .25rem;
  }
  .card>.header{
    display: flex;
    align-items: center;
    position: relative;
    height: .6rem;
    padding: 0 .19rem;
  }
  .card>.header:after{
    content:'';
    position: absolute;
    bottom: 0;
    left: 0;
    right: 0;
    background-color: #dbdbdb;
    height: 1px;
    transform-origin: 0 0;
    transform: scaleY(.5);
  }
  .card>.header .icon{
    height: .3rem;
    margin-right: .12rem;
  }
  .card>.header .icon>img{
    height: 100%;
  }
  .card>.header .title{
    font-size: .16rem;
    color: #06a8f4;
  }
  .card>.content{
    padding: .18rem;
  }
  .card>.table-content{
    padding: .09rem;
  }
  .section{
    font-size: .14rem;
    color: #333;
    word-wrap: break-word;
  }
  .wel-card .section{
    color: #fff;
  }
  .section+.section{
    margin-top: .1rem;
  }
  .section .title{
    color: #c48b66;
  }
  .section .title.red{
    color: #dd4433;
  }
  .section .title.green{
    color: #56c847;
  }
  .tip{
    display: flex;
    align-items: center;
    height: .45rem;
  }
  .tip>.icon{
    height: .16rem;
    margin-right: .09rem;
  }
  .tip>.icon>img{
    height: 100%;
  }
  .tip>.text{
    font-size: .16rem;
    color: #838587;
  }
  .table{
    width: 100%;
  }
  .table tr th{
    font-size: .12rem;
    color: #c69777;
    min-width: .55rem;
    height: .5rem;
    text-align: center;
  }
  .table tr td{
    font-size: .12rem;
    color: #2d2f31;
    height: .5rem;
    text-align: center;
    border-top: 1px dashed #dbdbdb;
  }
  .check-more {
    display: none;
    border-top: 1px dashed #dbdbdb;
    height: .5rem;
    line-height: .5rem;
    text-align: center;
    font-size: .14rem;
    color: #c48b66;
  }
  .card .footer{
    height: .5rem;
    padding: 0 .16rem;
    display: flex;
    align-items: center;
    position: relative;
  }
  .card .footer:before{
    content:'';
    position: absolute;
    top: 0;
    left: .08rem;
    right: .08rem;
    border-top: 2px dotted #dbdbdb;
    transform-origin: 0 0;
    transform: scaleY(.5);
  }
  .card .footer .icon{
    height: .14rem;
  }
  .card .footer .icon>img{
    height: 100%;
  }
  .card .footer .question-link{
    height: .5rem;
    line-height: .5rem;
    flex: 1;
    text-align: center;
    font-size: .14rem;
    color: #c48b66;
  }
  .wel-card .section{
    text-indent: .28rem;
  }
  .wel-card .section div{
    text-indent: 0!important;
  }
  .wel-words{
    font-size: .18rem;
    padding-top: .15rem;
    padding-bottom: .05rem;
    text-indent: 0!important;
  }
  .remark{
    font-size: .13rem;
    color: #b5b5b5;
  }
  .light{
    font-size: .13rem;
    /*color: #818181;*/
  }
  .h1{
    /*font-size: .15rem;*/
    font-weight: 400;
    color: #000;
  }

</style>
