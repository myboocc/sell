<template>
  <div>
    <v-header></v-header>
      <div class="tab-item">
        <a v-link="{path:'/goods'}">商品</a>
      </div>
      <div class="tab-item">
        <a v-link="{path:'/ratings'}">评论</a>
      </div>
      <div class="tab-item">
        <a v-link="{path:'/seller'}">商家</a>
      </div>
    <router-view></router-view>
  </div>
</template>

<script type="text/ecmascript-6">
  import header from 'components/header/header.vue';

  export default {
    components: {
      'v-header': header
    }
  };

</script>

<style type="text/css" rel="stylesheet">
/*#app {*/
  /*font-family: 'Avenir', Helvetica, Arial, sans-serif;*/
  /*-webkit-font-smoothing: antialiased;*/
  /*-moz-osx-font-smoothing: grayscale;*/
  /*text-align: center;*/
  /*color: #2c3e50;*/
  /*margin-top: 60px;*/
/*}*/

#app .tab{
	display: flex;
	width: 100%;
	height: 40px;
	line-height: 40px;
}
#app .tab .tab-item{
	flex: 1;
	text-align: center;
}
  #app .tab .tab-item > a{
    display: block;
    font-size: 14px;
    color: rgb(77, 85, 93);
  }
</style>
