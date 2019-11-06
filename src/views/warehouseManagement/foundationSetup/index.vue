<template>
<div id="app">
  <el-tabs type="card" tab-position="left" v-model="activeName">
    <el-tab-pane name="0">
      <span slot="label">供货商设置</span>
      <v-vendor v-if="activeName==0"></v-vendor>
    </el-tab-pane>
    <el-tab-pane name="1">
     <span slot="label">数据字典</span>
      <v-data v-if="activeName==1"></v-data>
    </el-tab-pane>
    <el-tab-pane name="2">
      <span slot="label">商品分类</span>
      <v-set v-if="activeName==2"></v-set>
    </el-tab-pane>
    <el-tab-pane name="3">
      <span slot="label">商品管理</span>
      <v-manage v-if="activeName==3"></v-manage>
    </el-tab-pane>
    <el-tab-pane name="4">
      <span slot="label">参数配置</span>
      <v-param v-if="activeName==4"></v-param>
    </el-tab-pane>
    <el-tab-pane name="5">
      <span slot="label">编号管理</span>
      <v-number v-if="activeName==5"></v-number>
    </el-tab-pane>

  </el-tabs>
  <router-view></router-view>
</div>
</template>

<script>
  import dataDictionary from './components/dataDictionary'
  import vendorSettings from './components/vendorSettings'
  import commodityClassification from './components/commodityClassification'
  import commodityManagement from './components/commodityManagement'
  import parameterConfiguration from './components/parameterConfiguration'
  import numberingManagement from './components/numberingManagement'
    export default {
        name: "index",
      data(){
          return {
            activeName: '0',
          }
      },
      methods:{

      },
      components: {
         'v-data': dataDictionary,
        'v-vendor':vendorSettings,
        'v-set': commodityClassification,
        'v-manage': commodityManagement,
        'v-param': parameterConfiguration,
        'v-number': numberingManagement
      }
    }
</script>

<style scoped>
  #app{
    width: 100%;
    padding-top: 20px;
  }
  ul{
    width: 150px;
  }
  ul li{
    list-style-type: none;
    line-height: 50px;
    background-color: #F0F2F5;
    font-size: small;
    text-align: center;
    border: #C0C4CC solid 1px;
  }
  .onClick{
    background-color: white;
  }
</style>
